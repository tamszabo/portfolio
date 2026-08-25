---
layout: post
title: "How I Structure Complex SQL Queries (and Why It Matters)"
date: 2026-04-08
image: /assets/images/11-sql-queries-header.png
categories: [Data Analysis, SQL, Best Practices]
description: "Learn how a senior data analyst structures complex SQL queries for readability and maintainability from row count checks to CTEs, explicit JOINs, and meaningful aliases."
author: Tamas Szabo
tags: [sql, data-analytics, best-practices, tutorial, sql-queries, cte, tableau]
---

# 🗂️ How I Structure Complex SQL Queries (and Why It Matters)

We've all been there. You open a query you wrote three months ago or worse, one a colleague left behind and you have no idea what it's doing. It technically runs. The results look plausible. But understanding *why* it does what it does takes longer than just rewriting it from scratch.

Over 8 years of writing SQL daily, I've developed a set of personal rules that keep my queries readable, debuggable, and easy to hand off. None of this is rocket science, but I rarely see it taught in courses. Here's exactly what I do.

---

## ✅ Before I write a single line: check the row count

This is the first thing I do, every time, without exception and it's the habit I wish someone had told me about early in my career.

Before touching the main query, I run this:

```sql
SELECT SUM(1) FROM main_table
```

Then I put the result in a comment right above my query:

```sql
-- Row count: 816,564
```

Why? Because this number is my sanity check throughout the entire build. If my final result has 2 million rows, I know immediately that something went wrong. Likely a fan-out from a bad join. If I skip this step, I might not catch it until a stakeholder questions the numbers. By then, trust is already eroded.

It takes five seconds. Do it every time.

---

## 🔗 I always use explicit JOINs

This is a hill I will die on.

Some people connect tables by listing them in the FROM clause and filtering in WHERE:

```sql
-- Please don't do this
SELECT *
FROM orders o, customers c, products p
WHERE o.customer_id = c.id
AND o.product_id = p.id
```

I find this extremely difficult to read. The join logic is buried inside the WHERE clause alongside the actual filters, which forces your brain to mentally separate two completely different concerns. It also makes it dangerously easy to accidentally produce a cartesian product.

Here's how I write the same thing:

```sql
SELECT *
FROM orders o
LEFT JOIN customers c ON o.customer_id = c.id
LEFT JOIN products p ON o.product_id = p.id
WHERE o.status = 'completed'
```

Notice I use **LEFT JOIN**, not just **JOIN**. This is intentional and important. A regular **JOIN** (also called an *INNER JOIN*) will silently drop any row from your main table that doesn't have a match in the joined table. In practice, this turns your join into an accidental filter and you might not even notice it in the results.

With **LEFT JOIN**, all rows from the main table are preserved. If there's no match in the joined table, you get a *NULL* instead of a missing row. That's a much safer default, and it makes data gaps visible rather than hiding them.

The join conditions and the filters live in separate, predictable places. Anyone reading this including future me can immediately see what's being connected and what's being filtered.

---

## 🏷️ Meaningful table aliases, not alphabet soup

Closely related: if you're aliasing your tables **a**, **b**, **c**, **d**, I promise your colleagues are not thanking you for it.

When a query has four or five tables, single-letter aliases tell you nothing. You're constantly scrolling back up to remember what *b* was. Instead, I use short but descriptive abbreviations based on the table name:

```sql
FROM account_identity ai
LEFT JOIN sales_funnel sf ON ai.account_id = sf.account_id
LEFT JOIN product_catalog pc ON sf.product_id = pc.id
```

**ai**, **sf**, **pc**: you don't need to look these up. They carry enough context to be self-explanatory throughout the query. Two or three characters is usually the sweet spot.

---

## 🧱 Build logic in layers with CTEs

Once the foundations are in place, I decompose complex logic into CTEs. Common Table Expressions. These are named, temporary result sets you define at the top of your query using the **WITH** keyword, and then reference like a regular table.

The rule I follow: **each CTE does exactly one thing.**

Here's a scenario where CTEs genuinely earn their place. I want to find customers who placed their first ever order in 2024, and then calculate how much they spent in total across all years. This requires two distinct logical steps that can't be cleanly collapsed into a single query.

```sql
-- Row count: 1,284,901

-- Step 1: Identify customers whose first order was in 2024
WITH first_order_per_customer AS (
    SELECT
        o.customer_id,
        MIN(o.order_date) AS first_order_date
    FROM orders o
    GROUP BY o.customer_id
),

new_customers_2024 AS (
    SELECT foc.customer_id
    FROM first_order_per_customer foc
    WHERE YEAR(foc.first_order_date) = 2024
),

-- Step 2: Calculate lifetime value for those customers
lifetime_value AS (
    SELECT
        o.customer_id,
        SUM(o.amount) AS total_revenue
    FROM orders o
    LEFT JOIN new_customers_2024 nc ON o.customer_id = nc.customer_id
    WHERE nc.customer_id IS NOT NULL
    GROUP BY o.customer_id
)

SELECT
    lv.customer_id,
    lv.total_revenue
FROM lifetime_value lv
ORDER BY lv.total_revenue DESC
```

Each CTE has a name that describes exactly what it contains. You can read the query top to bottom like a story: find each customer's first order, isolate those who started in 2024, then sum up everything they've ever spent. No nesting, no mental gymnastics.

---

## 📐 Order your CTEs like a reader would expect

The sequence of CTEs matters. I always follow this flow:

<div class="not-prose flex flex-col sm:flex-row gap-3 my-8">
    <div class="flex-1 p-4 bg-[#2a2a2a] border border-[#3c6e71]/30 rounded-2xl text-center">
        <p class="text-[#4a8e91] font-bold text-xs uppercase tracking-widest mb-1">1</p>
        <p class="text-white font-bold text-sm">Source</p>
        <p class="text-[#8a9a9b] text-xs mt-1">Raw or closest-to-source data</p>
    </div>
    <div class="flex-1 p-4 bg-[#2a2a2a] border border-[#3c6e71]/30 rounded-2xl text-center">
        <p class="text-[#4a8e91] font-bold text-xs uppercase tracking-widest mb-1">2</p>
        <p class="text-white font-bold text-sm">Filtered</p>
        <p class="text-[#8a9a9b] text-xs mt-1">Apply business rules and exclusions</p>
    </div>
    <div class="flex-1 p-4 bg-[#2a2a2a] border border-[#3c6e71]/30 rounded-2xl text-center">
        <p class="text-[#4a8e91] font-bold text-xs uppercase tracking-widest mb-1">3</p>
        <p class="text-white font-bold text-sm">Aggregated</p>
        <p class="text-[#8a9a9b] text-xs mt-1">Group, sum, count</p>
    </div>
    <div class="flex-1 p-4 bg-[#2a2a2a] border border-[#3c6e71]/30 rounded-2xl text-center">
        <p class="text-[#4a8e91] font-bold text-xs uppercase tracking-widest mb-1">4</p>
        <p class="text-white font-bold text-sm">Final</p>
        <p class="text-[#8a9a9b] text-xs mt-1">Shape the output</p>
    </div>
</div>

This mirrors how a reader's brain naturally processes logic and it means anyone can jump into the middle of your query and understand the context without reading the whole thing first.

---

## 💬 Comment the why, not the what

I don't comment every line that just adds noise. But I do annotate anywhere the business logic isn't obvious from the code alone:

```sql
-- Excluding test accounts created by the QA team (account_type = 'internal')
-- Revenue capped at contract value to avoid double-counting upsells
```

The code tells you *what* is happening. Comments should tell you *why* a decision was made. That distinction makes a huge difference when someone or you revisits the query six months later.

<div class="p-6 bg-[#3c6e71]/5 border-l-4 border-[#3c6e71] rounded-r-2xl my-8">
    <h4 class="text-white font-bold mb-2">A note on over-commenting</h4>
    <p class="text-[#b0bfc0] text-sm">Comments like <code>-- join orders to customers</code> above a JOIN are pure noise. If your table aliases and column names are clear, the code explains itself. Save comments for the decisions that aren't obvious — the business rules, the edge cases, the intentional exclusions.</p>
</div>

---

## 🎯 Putting it all together

None of these habits are individually groundbreaking. But together, they make your SQL feel intentional and professional and more importantly, they make it easy for others to build on your work.

Readable SQL is a form of communication. It signals that you're thinking about more than just getting the right answer. You're thinking about the person who comes after you.

**That's what separates a query that works from a query that lasts.**

<div class="not-prose mt-12 p-8 bg-[#3c6e71]/5 border border-[#3c6e71]/20 rounded-3xl text-center space-y-4">
    <h3 class="text-white font-bold text-xl">Want cleaner analytics output?</h3>
    <p class="text-[#b0bfc0] text-sm max-w-md mx-auto">I help companies turn messy data environments into executive-ready dashboards. Fixed scope, fixed price, delivered on time.</p>
    <a href="/work-with-me/" class="inline-block bg-[#3c6e71] hover:bg-[#4a8e91] text-white font-bold px-6 py-3 rounded-xl transition-all text-sm uppercase tracking-widest">
        Work With Me →
    </a>
</div>
