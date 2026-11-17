---
layout: default
title: "Writeups"
permalink: /writeups/
---
<section class="page-hero"><div class="eyebrow">01 / KNOWLEDGE BASE</div><h1>Write<span>ups.</span></h1><p>Practical breakdowns of vulnerabilities, labs, and exploitation techniques.</p></section>
<div class="post-list page-list">
{% assign posts = site.posts | where_exp: "post", "post.categories contains 'Writeups' or post.categories contains 'Web Security'" %}
{% for post in posts %}<a class="post-row" href="{{ post.url | relative_url }}"><span class="post-date">{{ post.date | date: "%Y.%m.%d" }}</span><span class="post-title">{{ post.title }}</span><span class="post-category">{{ post.categories | first }}</span><span class="post-arrow">↗</span></a>{% else %}<div class="empty-state"><h3>No writeups published yet.</h3><p>Add a Markdown post in <code>_posts/</code> with <code>categories: [Writeups]</code>.</p></div>{% endfor %}
</div>
