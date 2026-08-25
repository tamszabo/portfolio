---
layout: post
title: "Data Governance Explained: Why Your Numbers Don't Match (And What to Do About It)"
date: 2026-04-13
image: /assets/images/12-data-governance-header.png
categories: [Data Analysis, Best Practices, Data Governance, Career]
description: "Data governance explained for analysts: what it is, why it matters, and what happens when organizations ignore it. Real examples from enterprise data teams."
author: Tamas Szabo
tags: [data-governance, data-quality, analytics, kpi, data-management, enterprise-data]
---

# 🏛️ Data Governance Explained: Why Your Numbers Don't Match (And What to Do About It)

**What is a lead?**

At first it sounds like a simple question. But during my time working with Hyundai, this became a running joke. Ask ten people across ten countries and you'd get ten different answers. Some markets counted a test drive request as a lead. Others required a signed interest form. Some included online enquiries; others didn't. Nobody was wrong exactly. They just had different data, different processes, and no shared definition forcing them to align.

That's a data governance problem. And in my experience, it's far more common than most organizations want to admit.

---

## 🗂️ So what actually is data governance?

Data governance is the set of rules, processes, and responsibilities that determine how data is defined, accessed, and used across an organization. Think of it as the operating agreement for your data: who owns it, who can see it, what it means, and how it should be measured.

For analysts, this isn't abstract. Bad data governance is the reason you've sat in a meeting where two teams present conflicting sales numbers and nobody can explain why. It's the reason a simple question like "how many leads did we generate last month?" turns into a two-hour debate.

Good governance prevents that. Or at least, it makes it much less likely.

---

## 📊 Data quality & validation: when nobody agrees on the numbers

The scenario I saw repeatedly at large organizations: teams reporting different sales figures for the same period. Not because anyone was incompetent but because they were all working from slightly different data.

Some teams didn't have access to the same granularity as others. Some had taken an export, manually adjusted it to remove what they considered "noise," and then built their reporting on top of that modified version. The result? Every department had its own version of the truth, subtly shaped by their own assumptions and, sometimes, their own incentives to look good.

This is where data quality governance becomes critical. It means:

- **A single source of truth.** One certified dataset that everyone pulls from, rather than local copies that drift over time.
- **No manual edits to raw data.** Transformations happen in code, are versioned, and are visible to others not in an Excel file someone saved to their desktop.
- **Validation checks built into pipelines.** Row counts, null checks, range validations. Catching data issues before they reach a dashboard, not after a stakeholder spots them in a meeting.

As an analyst, even if you can't control your organization's entire data infrastructure, you can control your own work. Document your assumptions. Log your transformations. Make your logic auditable.

---

## 🔐 Access control & security: different data, different realities

One of the root causes of the "What is a lead?" problem was that each country had access to different data. Different systems, different fields, different histories. When people can only see a partial picture, they naturally build their understanding of the world around that partial picture and then defend it as truth.

Access control in data governance isn't just a security concern. It's a data consistency concern. When access is inconsistent and undocumented, you end up with:

- Teams drawing different conclusions because they're literally looking at different slices of reality.
- Nobody knowing exactly who has access to what, which makes audits painful.
- Sensitive data, personal customer information, salary data, financial forecasts. Visible to people who shouldn't be seeing it.

Good access governance means access is intentional, documented, and regularly reviewed. It also means that when access is restricted for legitimate reasons, there's a governed, aggregated alternative available so teams aren't flying blind or building their own workarounds.

<div class="p-6 bg-[#3c6e71]/5 border-l-4 border-[#3c6e71] rounded-r-2xl my-8">
    <h4 class="text-white font-bold mb-2">The patchwork quilt problem</h4>
    <p class="text-[#b0bfc0] text-sm">At big companies especially, the IT infrastructure often resembles a patchwork quilt. Every acquisition added a new system. Every new product launched its own database. Nobody ever stepped back to streamline it all — either because they didn't have the resources, or because it genuinely wasn't anyone's job to care. The result is a fragmented landscape where governance is essentially impossible to enforce consistently. That's not an excuse — it's a warning sign that governance needs to be a deliberate investment, not an afterthought.</p>
</div>

---

## 🎯 KPIs & metrics ownership: who decides what a **lead** is?

Back to that question. The reason **What is a lead?** became a joke at Hyundai is that nobody owned the definition in the beginning. So each market did what any rational team would do: they created their own. By the time the Marketing department stepped in to establish an official definition, it was already too late. Every country had built their reporting, their processes, and their understanding of the business around their own local version of the truth.

And here's the uncomfortable reality: even with a definition now officially on paper, changing it was nearly impossible. The infrastructure simply wasn't ready for it. There was no centralized solution that works across all markets. Each country sat on different systems, different data pipelines, different levels of access. Aligning them to a single definition would have required not just a policy change, but a complete overhaul of how data flowed across the organization.

This is the hidden danger of delayed governance. The longer an organization operates without clear definitions and ownership, the more entrenched the local workarounds become — and the harder it is to unwind them later.

Metrics ownership is one of the most underrated aspects of data governance. Every KPI your organization tracks should have:

<div class="not-prose grid grid-cols-1 md:grid-cols-3 gap-4 my-8">
    <div class="p-5 bg-[#2a2a2a] border border-[#3c6e71]/30 rounded-2xl">
        <p class="text-[#4a8e91] font-bold text-xs uppercase tracking-widest mb-2">A clear definition</p>
        <p class="text-[#b0bfc0] text-sm">Written down, agreed upon, and accessible not living in someone's head or buried in a slide deck from three years ago.</p>
    </div>
    <div class="p-5 bg-[#2a2a2a] border border-[#3c6e71]/30 rounded-2xl">
        <p class="text-[#4a8e91] font-bold text-xs uppercase tracking-widest mb-2">An owner</p>
        <p class="text-[#b0bfc0] text-sm">A specific person or team responsible for maintaining that definition and flagging when it needs to change.</p>
    </div>
    <div class="p-5 bg-[#2a2a2a] border border-[#3c6e71]/30 rounded-2xl">
        <p class="text-[#4a8e91] font-bold text-xs uppercase tracking-widest mb-2">A change process</p>
        <p class="text-[#b0bfc0] text-sm">If the business evolves and the definition needs updating, that change should be communicated, versioned, and applied consistently not quietly made by one team.</p>
    </div>
</div>

For analysts, this matters enormously. If you're building a dashboard that tracks leads, conversions, or revenue, you need to know which definition you're using, document it visibly, and flag any deviations. The worst thing you can do is assume everyone means the same thing when they say the same word.

---

## 💡 Why this matters more than you think

Data governance tends to get dismissed as a management or IT concern. Something senior people worry about, not analysts. I'd push back on that.

As an analyst, you are often the first person to notice when the numbers don't add up. You're the one who gets asked to reconcile two conflicting reports. You're the one building the dashboards that stakeholders use to make decisions.

That puts you in a uniquely important position. You might not be able to fix your company's entire data infrastructure but you can advocate for clearer definitions, push back when data is modified without documentation, and build your own work in a way that's transparent and auditable.

Data governance isn't bureaucracy. It's what makes your work trustworthy.

---

## 🧭 You can't be data-driven without data governance

Every organization wants to be data-driven. It's in the strategy decks, the all-hands presentations, the job descriptions. But data-driven decision making only works if everyone is driving with the same map.

If your leads mean something different in Germany than they do in Korea, you're not data-driven. You're opinion-driven with a spreadsheet attached. If your sales figures change depending on which team you ask, you're not measuring reality you're measuring each team's version of it. If your infrastructure is a patchwork of systems that nobody fully understands, your dashboards are built on sand.

Data governance is what turns raw data into something you can actually trust. It's not glamorous work. It doesn't ship features or close deals. But without it, every insight is questionable, every report is a negotiation, and every dashboard is one awkward stakeholder question away from falling apart.

**You can't be data-driven without data governance. And now that you know what it looks like when it's missing, you'll start seeing it everywhere.**

<div class="not-prose mt-12 p-8 bg-[#3c6e71]/5 border border-[#3c6e71]/20 rounded-3xl text-center space-y-4">
    <h3 class="text-white font-bold text-xl">Suspect your BI setup has a governance problem?</h3>
    <p class="text-[#b0bfc0] text-sm max-w-md mx-auto">A Dashboard Audit is often the fastest way to surface conflicting definitions, undocumented assumptions, and KPIs nobody actually owns.</p>
    <a href="/work-with-me/" class="inline-block bg-[#3c6e71] hover:bg-[#4a8e91] text-white font-bold px-6 py-3 rounded-xl transition-all text-sm uppercase tracking-widest">
        See the Dashboard Audit →
    </a>
</div>
