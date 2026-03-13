---
layout: post
title: "Makeover Monday: Redesigning Financial Markets Data in Tableau"
date: 2026-03-13
image: /assets/images/6-financial-markets.png
categories: [DataViz, Data Analysis]
description: "Makeover Monday is the weekly challenge that keeps my Tableau skills sharp. Here's how I redesigned a financial markets dataset — the design decisions, the data story, and the live dashboard."
author: Tamas Szabo
---

# 📈 What Is Makeover Monday?

If you work in data and you're not doing Makeover Monday, you're leaving skill development on the table.

[Makeover Monday](https://www.makeovermonday.co.uk/) is a free, weekly data visualisation challenge started by Andy Kriebel and Eve Barratt. Every Monday, a dataset is published — anything from global energy consumption to sports statistics to financial markets — along with an original chart that represents it. Your job is to redesign it. Better story, better design, better clarity. Then share it with the community on Tableau Public and social media.

There are no formal prizes or leaderboard — though occasionally a submission earns a [Viz of the Day](https://public.tableau.com/app/discover/viz-of-the-day) feature from Tableau Public, which is a genuine honour in the community. Mostly though it is a weekly discipline that forces you to think critically about how data is visualised — and to actually build something.

## 🏋️ Why It Matters

Most analysts I've worked with are technically proficient but have had little exposure to visual design principles. They know how to aggregate data and build calculated fields, but they've never asked *why* they chose a bar chart over a line chart, or why their KPI tiles are green when the business is struggling.

Makeover Monday fixes this in a way no tutorial can, because it puts you in front of a real dataset, a real original visualisation, and a community of hundreds of other analysts doing the same thing. You start to develop opinions. You learn to justify your choices. You build a portfolio of work that demonstrates not just technical skill but editorial judgment.

It's also a forcing function. Knowing that every Monday has a deadline means you actually finish things — which is the single biggest difference between analysts who grow and analysts who don't.

---

## 💹 2024 Week 40 Challenge: Financial Markets

This submission is from Week 40 of 2024. The dataset covers 6 financial market performance. The original chart was a line chart with a table. Functional report with conservative design.

My redesign goal was to turn it into something executive-ready: a dashboard that answers the question *"how are the markets performing?"* before the viewer has read a single number.

---

## 🎨 The Design Decisions

**Dark mode as the foundation**

Financial data lives in terminal screens and Bloomberg dashboards. Dark mode isn't an aesthetic choice here — it's a contextual signal. A navy background immediately reads as "financial" to anyone who has spent time in that world. It also handles colour contrast better: green gains and red losses pop against dark backgrounds in a way they never do on white.

I used `#212529` as the base — a dark charcoal that feels more at home in a financial context, and provides just enough warmth to avoid the cold, clinical feel of a true black background.

**Dark-themed line chart**

The original used a standard light-themed line chart to show index performance over time — clean, but visually flat and undifferentiated from any default Tableau output. I kept the line chart format since it's the right choice for continuous price movement across time, but reskinned it completely to the dark theme. Against a `#212529` background, each index line reads with much more contrast and intentionality. The data being visualised is the same as in the [original source](https://curvo.eu/backtest/en/compare-indexes/euro-stoxx-50-vs-ftse-100-vs-msci-china-vs-nasdaq-100-vs-nyse-arca-gold-bugs-vs-sp-500?currency=usd) — Euro Stoxx 50, FTSE 100, MSCI China, Nasdaq 100, NYSE Arca Gold Bugs, and S&P 500 — the difference is entirely in how that data is presented.

**Individual KPIs instead of a table**

The original placed a summary table beneath the line chart — six rows of numbers that required the viewer to scan horizontally and mentally compare values. I replaced this with individual KPI tiles, one per market. Each tile shows the index name and its return at a glance, coloured blue or pink. No scanning required — the viewer's eye moves across six tiles and the comparison happens instantly.

Blue = positive return, pink = negative return. That's the only colour logic in the entire dashboard. When every colour has one job and one job only, the viewer reads the data without thinking about it.

---

## 📊 The Data Story

The financial markets data has a deceptive first impression — and that's exactly what makes it interesting.

At first glance, the line chart looks like a broad bull market story. Most lines trend upward from the starting point and the overall picture reads as positive. But look closer and one index breaks the pattern completely: MSCI China declined significantly over the period, moving in the opposite direction to every other market in the dataset.

This is the kind of insight that gets lost in a table. When six rows of numbers are presented side by side, the eye averages them — it sees "mostly positive" and moves on. When the same data is plotted as lines on a shared axis, the divergence becomes impossible to miss. One line goes down while five go up, and suddenly the story changes from "markets performed well" to "global markets performed well — except China."

That's the difference between data that informs and data that misleads by omission.

---

## 📺 Live Dashboard

Explore the full interactive version below. Hover over any element for the underlying data, and use the toolbar to filter by time period:

<div class="not-prose my-10">
    <div class="w-full rounded-2xl overflow-hidden border border-slate-700 shadow-2xl">
        <div class='tableauPlaceholder' id='viz1773385905398' style='position: relative; width: 100%;'>
            <noscript>
                <a href='#'>
                    <img alt='Financial Markets' src='https://public.tableau.com/static/images/Fi/FinancialMarkets_17280507711200/FinancialMarkets/1_rss.png' style='border: none' />
                </a>
            </noscript>
            <object class='tableauViz' style='display:none;'>
                <param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' />
                <param name='embed_code_version' value='3' />
                <param name='site_root' value='' />
                <param name='name' value='FinancialMarkets_17280507711200/FinancialMarkets' />
                <param name='tabs' value='no' />
                <param name='toolbar' value='yes' />
                <param name='static_image' value='https://public.tableau.com/static/images/Fi/FinancialMarkets_17280507711200/FinancialMarkets/1.png' />
                <param name='animate_transition' value='yes' />
                <param name='display_static_image' value='yes' />
                <param name='display_spinner' value='yes' />
                <param name='display_overlay' value='yes' />
                <param name='display_count' value='yes' />
                <param name='language' value='en-US' />
            </object>
        </div>
        <script type='text/javascript'>
            var divElement = document.getElementById('viz1773385905398');
            var vizElement = divElement.getElementsByTagName('object')[0];
            vizElement.style.width = '100%';
            vizElement.style.height = (divElement.offsetWidth * 0.73) + 'px';
            var scriptElement = document.createElement('script');
            scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';
            vizElement.parentNode.insertBefore(scriptElement, vizElement);
        </script>
    </div>
    <p class="text-slate-500 text-xs text-center mt-3 font-mono">Interactive — hover over any element to explore the data. <a href="https://public.tableau.com/app/profile/tamasszabo/viz/FinancialMarkets_17280507711200/FinancialMarkets" target="_blank" class="text-indigo-400 hover:underline">Open full screen on Tableau Public →</a></p>
</div>

---

## 🔁 The Makeover Monday Habit

I treat Makeover Monday the same way I treat my home workouts. You don't do it because every session feels great. You do it because the compound effect of showing up every week is real and measurable — and because the weeks you skip are always the ones you regret.

If you're an analyst and you're not already doing it, start this Monday. The dataset takes 10 minutes to download. You don't need a perfect viz — you need a finished one. The community is generous with feedback and the learning curve is steep in exactly the right direction.

The archive of everything I've built for Makeover Monday is on my [Tableau Public profile](https://public.tableau.com/app/profile/tamasszabo/vizzes). Each one is a snapshot of where my thinking was that week — which means looking back through them is one of the most honest performance reviews I've ever done.

<div class="not-prose mt-12 grid grid-cols-1 md:grid-cols-2 gap-6">

    <!-- Community CTA -->
    <div class="p-8 bg-indigo-500/5 border border-indigo-500/20 rounded-3xl space-y-4">
        <p class="text-indigo-400 font-black text-xs uppercase tracking-widest">Join the Challenge</p>
        <h3 class="text-white font-bold text-xl leading-snug">Try Makeover Monday yourself</h3>
        <p class="text-slate-400 text-sm">Every Monday, a new dataset. Free, open to everyone, and genuinely the best Tableau practice you'll find.</p>
        <a href="https://www.makeovermonday.co.uk/" target="_blank"
           class="inline-block border border-indigo-500 text-indigo-400 hover:bg-indigo-500 hover:text-white font-bold px-6 py-3 rounded-xl transition-all text-sm uppercase tracking-widest">
            makeovermonday.co.uk →
        </a>
    </div>

    <!-- Tableau profile CTA -->
    <div class="p-8 bg-indigo-500/10 border border-indigo-500/40 rounded-3xl space-y-4">
        <p class="text-indigo-400 font-black text-xs uppercase tracking-widest">My Work</p>
        <h3 class="text-white font-bold text-xl leading-snug">See the full archive</h3>
        <p class="text-slate-400 text-sm">Every Makeover Monday viz I've published — plus executive dashboards, sport analytics, and more on Tableau Public.</p>
        <a href="https://public.tableau.com/app/profile/tamasszabo/vizzes" target="_blank"
           class="inline-block bg-indigo-500 hover:bg-indigo-400 text-white font-bold px-6 py-3 rounded-xl transition-all text-sm uppercase tracking-widest">
            View Tableau Profile →
        </a>
    </div>

</div>
