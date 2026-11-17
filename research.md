---
layout: default
title: "Research"
permalink: /research/
---
<section class="page-hero"><div class="eyebrow">02 / DEEP DIVES</div><h1>Research<span>.</span></h1><p>Experiments, technical notes, vulnerability analysis, and security observations.</p></section>
<div class="post-list page-list">
{% assign posts = site.posts | where_exp: "post", "post.categories contains 'Research'" %}
{% for post in posts %}<a class="post-row" href="{{ post.url | relative_url }}"><span class="post-date">{{ post.date | date: "%Y.%m.%d" }}</span><span class="post-title">{{ post.title }}</span><span class="post-category">RESEARCH</span><span class="post-arrow">↗</span></a>{% else %}<div class="empty-state"><h3>Research log is empty.</h3><p>Publish a post with <code>categories: [Research]</code> to list it here.</p></div>{% endfor %}
</div>
