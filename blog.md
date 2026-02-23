---
layout: default
title: Blog
permalink: /blog/
---

<h1 class="text-4xl font-black text-white mb-12">Articles & Insights</h1>

<div class="grid gap-8">
  {% for post in site.posts %}
    <a href="{{ post.url }}" class="block p-8 bg-slate-800/50 border border-slate-700 rounded-2xl hover:border-indigo-500 transition">
      <span class="text-indigo-400 text-sm font-mono">{{ post.date | date: "%B %d, %Y" }}</span>
      <h2 class="text-2xl font-bold text-white mt-2">{{ post.title }}</h2>
      <p class="text-slate-400 mt-4">{{ post.excerpt | strip_html | truncate: 160 }}</p>
    </a>
  {% endfor %}
</div>