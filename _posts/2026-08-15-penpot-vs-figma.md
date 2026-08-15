---
layout: post
title: "Penpot vs. Figma for Data Visualization Framing"
date: 2026-08-15
image: "/assets/images/14-penpot-vs-figma-header.png"
categories: [Career, DataViz, Data Analysis, Open Source]
description: "Figma is my go-to design tool — but Penpot is making me question that. An honest comparison of both tools from an analyst's perspective, and why I haven't fully switched yet."
series: "The Analyst's Toolkit"
series_part: 5
author: Tamas Szabo
---
# 🛠 The Analyst's Toolkit IV.

This post is also a small manifesto. I've become genuinely passionate about open source software lately, and **Penpot** is one of the most exciting examples of what open source can look like when it's done right.

If you've followed this series, you know I've been building my design workflow around a small set of tools: **Figma** for wireframing and layout, **Coolors** for colour palette building, and **Tableau Public** for the actual visualisations. Today I want to introduce a tool that's been sitting in the back of my mind for a while — Penpot — and talk honestly about why I haven't fully switched to it yet, even though I really want to.

---

## 🏢 Who's Behind Each Tool?

Before comparing features, it's worth understanding who you're actually depending on when you choose a tool.

**[Figma](https://www.figma.com/)** was founded by Dylan Field and is based in San Francisco. After a high-profile attempted acquisition fell through in 2024, Figma went public in 2025 — making it one of the more anticipated tech IPOs of recent years. It's now a publicly traded company, which brings its own set of pressures around growth, monetisation, and shareholder expectations.

**[Penpot](https://penpot.app/)** is built by Kaleidos, a Madrid-based startup founded in 2011 by Pablo Ruiz-Múzquiz and Enrique Posner. The platform is on a mission to bridge the gap between designers and developers, and today over 80,000 teams run on Penpot — including Mozilla, Accenture, IBM, Google, and Microsoft. It's not a scrappy side project. It's a serious, growing platform with a clear philosophical mission: design tooling should be open, free, and owned by nobody.

The ownership question matters more than it might seem. Because Penpot is open source, it cannot be discontinued or paywalled retroactively. That's a guarantee Figma — now accountable to public market shareholders — simply cannot offer.

---

## ✅ What Figma Does Well

Let's be honest — Figma is the industry standard for good reason.

It's fast, polished, and the collaboration experience is genuinely excellent. Real-time multiplayer editing, comments, design tokens, a mature component system, and a plugin ecosystem with a solution for almost every niche need. Every designer you hire already knows it, every plugin you might want already exists, and every design system reference you find online ships as a Figma library.

For analysts using Figma to frame dashboards — sketching layouts, defining colour systems, wireframing before building in Tableau — it's a smooth, friction-free experience. The auto-layout system is powerful, and once you've internalised how it works, it's genuinely fast to use.

The tradeoff? As a publicly traded company, Figma is now under pressure to grow revenue. Price hikes, feature paywalling, and shifting priorities are real risks for any tool that's gone from an independent startup to a listed company. Your designs live in Figma's cloud, under Figma's terms — and those terms will increasingly be shaped by what Wall Street expects.

---

## 🌱 What Penpot Does Well

Penpot is no longer just an "open source alternative." With the release of Penpot 2.0, it has become a mature tool that offers features Figma still doesn't have — like true CSS Grid. For analysts, that might sound like a developer concern, but it matters for layout precision.

A few things Penpot genuinely gets right:

* **It's completely free.** Not a freemium model with paywalled collaboration — actually free. You can use the hosted version at no cost, or self-host it entirely on your own infrastructure, which is a significant advantage for organisations with data sovereignty requirements.
* **Open standards.** Penpot is built on open web standards including SVG, CSS, HTML, and JSON, making designs natively accessible to developers. Your files aren't locked into a proprietary format — they're portable by design.
* **Self-hosting option.** Unlike Figma where everything is in the cloud, Penpot can be installed on your own servers. For teams working with sensitive data or in regulated industries, this is a genuinely meaningful differentiator.
* **Prototyping that actually innovates.** Penpot's timeline-based animation system outshines Figma's basic transitions, offering sophisticated interaction design without the artificial limitations Figma imposes through premium pricing.

---

## ⚠️ Where Penpot Still Has Ground to Cover

I want to be fair here because I genuinely root for Penpot — but honesty matters more than cheerleading.

There's no equivalent to Figma's auto-layout, which is a significant limitation for responsive design work. Colour management is functional but basic, and there's no equivalent to Figma's robust variable system for managing design tokens at scale.

Figma's maturity still provides undeniable polish, scale, and enterprise stability. The synchronous editing and performance on massive design systems generally remain a high bar. Performance can also be an issue in Penpot — files can render slowly, and some users report placeholder images appearing when zooming on the canvas. These are the kinds of friction points that slow you down when you're trying to work quickly.

---

## 🏁 My Honest Conclusion

I love what Penpot stands for. Open source, community-driven, free from corporate ownership — these are values I genuinely believe in, and I want to support tools that embody them.

But I'll be honest: **I can't make the full switch yet.** I've spent years building muscle memory in Figma. I know where everything is. I know how auto-layout behaves. I know how to move fast. Switching to Penpot right now would slow me down in ways that would affect my actual work — and that's a real cost, even when the reasons to switch are compelling.

So where does that leave me? Penpot is already in my toolkit as a tool I experiment with and keep an eye on. Every release it gets closer. The gap is narrowing. And the moment the friction of switching feels smaller than the discomfort of staying on a platform driven by public market expectations, I'll make the move.

For now: **if you're starting fresh with no Figma habits to unlearn, I'd genuinely recommend giving Penpot a serious look.** The concept is right. The direction is right. And the open source community deserves your support.

<div class="not-prose mt-12 p-8 bg-[#3c6e71]/5 border border-[#3c6e71]/20 rounded-3xl text-center space-y-4">
    <h3 class="text-white font-bold text-xl">Want to build something together?</h3>
    <p class="text-[#b0bfc0] text-sm">If you need executive-ready dashboards built with this approach, let's talk.</p>
    <a href="/work-with-me/#contact" class="inline-block bg-[#3c6e71] hover:bg-[#4a8e91] text-white font-bold px-6 py-3 rounded-xl transition-all text-sm uppercase tracking-widest">
        Get in Touch →
    </a>
</div>
