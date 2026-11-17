---
layout: default
title: "Home"
description: "0xMr057N — Security Research, Web Pentesting and Vulnerability Writeups."
---
<section class="hero">
  <div class="hero-grid"></div>
  <div class="eyebrow"><span class="status-dot"></span> INDEPENDENT SECURITY RESEARCHER</div>
  <h1>Breaking Things.<br><span>Understanding Why.</span></h1>
  <p class="hero-copy">A field journal on web security, penetration testing, vulnerability research, and the tools built along the way.</p>
  <div class="hero-actions">
    <a class="button button-primary" href="#latest">Explore writeups <span>→</span></a>
    <a class="button button-ghost" href="https://github.com/OmarElhemaly" target="_blank" rel="noopener">GitHub ↗</a>
  </div>
  <div class="hero-terminal"><span class="terminal-prompt">omar@0xmr057n:~$</span> whoami<br><span class="terminal-output">web security · pentesting · research</span><span class="terminal-cursor">▌</span></div>
</section>
<section class="section" id="focus">
  <div class="section-heading"><div><div class="eyebrow">01 / WHAT I EXPLORE</div><h2>Areas of focus</h2></div></div>
  <div class="focus-grid">
    <a class="focus-card" href="{{ '/writeups/' | relative_url }}"><span class="card-index">01</span><span class="focus-icon">⌘</span><h3>Web Security</h3><p>Web vulnerabilities, exploitation paths, and practical defenses.</p><span class="card-arrow">↗</span></a>
    <a class="focus-card" href="{{ '/research/' | relative_url }}"><span class="card-index">02</span><span class="focus-icon">⌬</span><h3>Research & Writeups</h3><p>Lab notes, methodology, root-cause analysis, and lessons learned.</p><span class="card-arrow">↗</span></a>
    <a class="focus-card" href="{{ '/tools/' | relative_url }}"><span class="card-index">03</span><span class="focus-icon">⌁</span><h3>Tools & Scripts</h3><p>Small utilities and experiments for authorized security testing.</p><span class="card-arrow">↗</span></a>
  </div>
</section>
<section class="section" id="latest">
  <div class="section-heading"><div><div class="eyebrow">02 / THE KNOWLEDGE BASE</div><h2>Latest transmissions</h2></div><a class="text-link" href="{{ '/writeups/' | relative_url }}">All posts ↗</a></div>
  <div class="post-list">
  {% assign posts = site.posts | slice: 0, 8 %}
  {% for post in posts %}
    <a class="post-row" href="{{ post.url | relative_url }}"><span class="post-date">{{ post.date | date: "%Y.%m.%d" }}</span><span class="post-title">{{ post.title }}</span><span class="post-category">{{ post.categories | first | default: "NOTE" }}</span><span class="post-arrow">↗</span></a>
  {% else %}
    <div class="empty-state"><span class="empty-icon">[ _ ]</span><h3>No transmissions yet.</h3><p>The first writeup is being prepared. Check back soon.</p></div>
  {% endfor %}
  </div>
</section>
<section class="cta-band"><div class="eyebrow">STAY CURIOUS / STAY SHARP</div><h2>Every vulnerability has a story.</h2><p>Let's understand the root cause, not just the payload.</p><a class="text-link" href="https://github.com/OmarElhemaly" target="_blank" rel="noopener">Follow the work on GitHub ↗</a></section>
