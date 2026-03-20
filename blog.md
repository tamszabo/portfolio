---
layout: default
title: Blog
permalink: /blog/
---

<header class="mb-16">
    <h1 class="text-5xl font-black text-white tracking-tight italic uppercase">
        Articles <span class="text-[#3c6e71]">&</span> Insights
    </h1>
    <p class="text-[#b0bfc0] mt-4 text-lg max-w-2xl">
        Thoughts on data strategy, dashboard design, and bridging the gap between raw numbers and executive decisions.
    </p>
</header>

<div class="grid gap-6">
    {% for post in site.posts %}
    <a href="{{ post.url | relative_url }}" class="group block p-8 bg-[#2a2a2a]/40 border border-[#3c6e71] rounded-3xl hover:border-[#3c6e71] transition-all duration-300 shadow-xl hover:shadow-[#3c6e71]/10">
        
        <div class="flex flex-col md:flex-row gap-8 items-start md:items-center">
            
            {% if post.image %}
            <div class="w-full md:w-64 h-40 flex-shrink-0 overflow-hidden rounded-2xl border border-[#3c6e71]">
                <img src="{{ post.image | relative_url }}" 
                     class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500" 
                     alt="{{ post.title }}">
            </div>
            {% endif %}

            <div class="flex-grow space-y-2">
                <div class="flex justify-between items-start">
                    <span class="text-[#4a8e91] text-xs font-mono uppercase tracking-widest">
                        {{ post.date | date: "%B %d, %Y" }}
                    </span>
                    <div class="flex items-center gap-3">
                        {% assign words = post.content | number_of_words %}
                        {% assign reading_time = words | divided_by: 200 | plus: 1 %}
                        <span class="text-[#8a9a9b] text-xs font-mono">{{ reading_time }} min read</span>
                        <div class="md:hidden">
                            <span class="text-white">→</span>
                        </div>
                    </div>
                </div>
                
                <h2 class="text-2xl font-bold text-white group-hover:text-[#4a8e91] transition-colors leading-tight">
                    {{ post.title }}
                </h2>
                
                <p class="text-[#b0bfc0] text-sm leading-relaxed max-w-2xl">
                    {{ post.excerpt | strip_html | truncate: 160 }}
                </p>

                {% if post.categories %}
                <div class="flex gap-2 pt-2">
                    {% for category in post.categories %}
                    <span class="px-3 py-1 bg-[#252525] text-[#b0bfc0] text-[10px] font-bold uppercase rounded-full">
                        {{ category }}
                    </span>
                    {% endfor %}
                </div>
                {% endif %}
            </div>

            <div class="hidden md:block flex-shrink-0">
                <span class="inline-flex items-center justify-center w-12 h-12 rounded-full bg-[#2a2a2a] group-hover:bg-[#284b63] text-white transition-all transform group-hover:translate-x-2">
                    →
                </span>
            </div>
        </div>
    </a>
    {% endfor %}
</div>

{% if site.posts.size == 0 %}
<div class="text-center py-20 border border-dashed border-[#3c6e71] rounded-3xl">
    <p class="text-[#8a9a9b] italic">No posts yet. Stay tuned!</p>
</div>
{% endif %}
