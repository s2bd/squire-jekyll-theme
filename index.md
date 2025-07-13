---
layout: default
title: Home
---
<div class="card">
  <div class="hero-section">
    <h1>Welcome to {{ site.title }}</h1>
    <p class="hero-subtitle">{{ site.description }}</p>
  </div>

  <div class="posts-section">
    <h2>Latest Articles</h2>

    {% for post in site.posts %}
      <div class="post-preview">
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
        <p>{{ post.excerpt | strip_html | truncate: 200 }}</p>
      </div>
    {% endfor %}
  </div>
</div>
