---
layout: default
title: Blog
permalink: /blog/
---

<header class="mb-16">
    <h1 class="text-5xl font-black text-white tracking-tight italic uppercase">
        Articles <span class="text-indigo-500">&</span> Insights
    </h1>
    <p class="text-slate-400 mt-4 text-lg max-w-2xl">
        Thoughts on data strategy, dashboard design, and bridging the gap between raw numbers and executive decisions.
    </p>
</header>

<div class="grid gap-6">
    {% for post in site.posts %}
    <a href="{{ post.url | relative_url }}" class="group block p-8 bg-slate-800/40 border border-slate-700 rounded-3xl hover:border-indigo-500 transition-all duration-300 shadow-xl hover:shadow-indigo-500/10">
        <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
            <div class="space-y-2">
                <span class="text-indigo-400 text-xs font-mono uppercase tracking-widest tracking-widest">
                    {{ post.date | date: "%B %d, %Y" }}
                </span>
                <h2 class="text-2xl font-bold text-white group-hover:text-indigo-400 transition-colors">
                    {{ post.title }}
                </h2>
                <p class="text-slate-400 text-sm leading-relaxed max-w-2xl">
                    {{ post.excerpt | strip_html | truncate: 180 }}
                </p>
            </div>
            <div class="flex-shrink-0">
                <span class="inline-flex items-center justify-center w-12 h-12 rounded-full bg-slate-700 group-hover:bg-indigo-600 text-white transition-all transform group-hover:translate-x-2">
                    →
                </span>
            </div>
        </div>
        
        {% if post.categories %}
        <div class="flex gap-2 mt-6">
            {% for category in post.categories %}
            <span class="px-3 py-1 bg-slate-900 text-slate-400 text-[10px] font-bold uppercase rounded-full">
                {{ category }}
            </span>
            {% endfor %}
        </div>
        {% endif %}
    </a>
    {% endfor %}
</div>

{% if site.posts.size == 0 %}
<div class="text-center py-20 border border-dashed border-slate-700 rounded-3xl">
    <p class="text-slate-500 italic">No posts yet. Stay tuned!</p>
</div>
{% endif %}
