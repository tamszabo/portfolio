---
layout: post
title: "Makeover Monday: The Weekly Habit That Sharpens Every Analyst"
date: 2026-03-14
image: /assets/images/6-makeover-monday.png
categories: [Career, DataViz, Data Analysis]
description: "Makeover Monday is the best weekly practice habit in data visualization. Here's how I use it to stay sharp, build my portfolio, and think like a better analyst — one dataset at a time."
series: "The Analyst's Toolkit"
series_part: 4
author: Tamas Szabo
---

# 📅 The Analyst's Toolkit IV.

Every musician practices scales. Every athlete does drills. Every writer keeps a journal.

Data analysts? Most of us wait for the next project brief.

That's a mistake — and **[Makeover Monday](https://www.makeovermonday.co.uk/)** is the fix.

---

## 🔄 What Is Makeover Monday?

Makeover Monday is a free, weekly data visualization challenge. Every week, the organizers publish a dataset and an existing chart. Your job is simple: **take the data, redesign the visual, and share it.**

No brief. No boss. No stakeholder asking for an Excel export.

Just you, the data, and a blank Tableau canvas.

The community has been running since 2016, with thousands of submissions published publicly on Tableau Public every week. That means you're not just practicing in isolation — you're contributing to one of the largest open data viz communities in the world.

---

## 🏋️ Why I Treat It as a Weekly Drill

When I joined **Starschema**, I was surrounded by analysts who were genuinely exceptional at Tableau. The gap between where I was and where they were felt enormous. Reading documentation wasn't closing it. Watching tutorials wasn't closing it either.

What actually moved the needle was **deliberate repetition on real data** — and Makeover Monday gave me exactly that.

Here's what a typical week looks like for me:

<div class="not-prose grid grid-cols-1 md:grid-cols-3 gap-4 my-8">
    <div class="flex flex-col gap-2 p-5 bg-slate-800/40 border border-slate-700 rounded-2xl">
        <span class="text-indigo-400 font-black text-xs uppercase tracking-widest">Monday</span>
        <span class="text-white font-bold text-sm">Download the dataset</span>
        <span class="text-slate-400 text-sm">Look at the original chart. Note what's working and — more importantly — what isn't. What story is it trying to tell? Is it succeeding?</span>
    </div>
    <div class="flex flex-col gap-2 p-5 bg-slate-800/40 border border-slate-700 rounded-2xl">
        <span class="text-indigo-400 font-black text-xs uppercase tracking-widest">Tuesday–Wednesday</span>
        <span class="text-white font-bold text-sm">Build the redesign</span>
        <span class="text-slate-400 text-sm">One to two hours maximum. The time constraint is intentional — it mirrors real corporate deadlines and forces you to make decisions instead of perfecting forever.</span>
    </div>
    <div class="flex flex-col gap-2 p-5 bg-slate-800/40 border border-slate-700 rounded-2xl">
        <span class="text-indigo-400 font-black text-xs uppercase tracking-widest">Thursday–Friday</span>
        <span class="text-white font-bold text-sm">Publish and review</span>
        <span class="text-slate-400 text-sm">Post to Tableau Public. Then spend 20 minutes browsing other submissions. This is where the real learning happens — you'll see approaches you'd never have thought of.</span>
    </div>
</div>

That's it. Three to four hours per week, consistently applied over months, compounds into a skill level that no course can replicate.

---

## 💡 What It Actually Teaches You

Most analysts think Makeover Monday is about making prettier charts. It isn't. After years of doing it, here's what it actually trains:

**Critical thinking about existing visuals.** Every week starts with the same question: *what is wrong with this chart?* After a year of asking that question weekly, you develop an instinct for spotting bad data communication instantly — in client dashboards, in board presentations, in your own work.

**Speed.** The self-imposed time constraint teaches you to make a good decision in two minutes rather than a perfect decision in two hours. That speed is exactly what separates senior analysts from junior ones in a corporate environment.

**Breadth of data domains.** One week it's financial markets. The next it's global health data. Then climate, then sport, then economics. Each dataset forces you to think about what chart type actually fits *this* data — not the chart type you're most comfortable with.

**A public portfolio, built automatically.** Every submission you publish becomes a Tableau Public viz with a shareable URL. By the end of a year, you have 40+ pieces of work, spanning dozens of topics and chart types, all publicly visible to recruiters and clients.

---

## 📊 My Entry: Financial Markets

To show you what this looks like in practice, here's one of my own Makeover Monday submissions — a redesign of a financial markets dataset.

The original chart presented the data as a dense table with conditional formatting. Readable, yes. But it buried the trend and forced the viewer to do the analytical work themselves.

My redesign focused on making the market movement immediately legible — pulling the signal out of the noise so the viewer understands the story before they read a single number.

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

## 🚀 How to Get Started

If you've never participated before, the barrier is lower than you think:

1. Go to **[makeovermonday.co.uk](https://www.makeovermonday.co.uk/)** and download the current week's dataset
2. Open Tableau Public (free) and build something — anything — in under two hours
3. Publish to your Tableau Public profile
4. Share it on LinkedIn or X with the hashtag **#MakeoverMonday**

That's the entire process. 

<div class="p-6 bg-indigo-500/5 border-l-4 border-indigo-500 rounded-r-2xl my-8">
    <h4 class="text-white font-bold mb-2">💡 One rule I follow</h4>
    <p class="text-slate-400 text-sm">I never look at other people's submissions <em>before</em> I build mine. The moment you see someone else's elegant solution, your brain stops exploring and starts copying. Protect your creative process — publish first, browse second.</p>
</div>

---

## 🔑 The Takeaway

Tableau Public gave me the stage. Figma gave me the blueprint. Coolors gave me the palette. But Makeover Monday gave me the **repetitions**.

Skill in data visualization is not built by reading about it. It's built by doing it, weekly, on real data, in public, under a self-imposed deadline — and then honestly reviewing the gap between what you made and what the best submissions looked like.

That gap closes faster than you'd expect. But only if you show up every week.

<div class="not-prose mt-12 p-8 bg-indigo-500/5 border border-indigo-500/20 rounded-3xl text-center space-y-4">
    <h3 class="text-white font-bold text-xl">The Toolkit Series continues</h3>
    <p class="text-slate-400 text-sm">Tableau Public → Figma → Coolors → Makeover Monday — the full practice stack, one post at a time.</p>
    <a href="/blog/" class="inline-block bg-indigo-500 hover:bg-indigo-400 text-white font-bold px-6 py-3 rounded-xl transition-all text-sm uppercase tracking-widest">
        See All Posts →
    </a>
</div>

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
