---
layout: default
title: Home
---
# Welcome to {{ site.title }}

Below are my latest blog posts:

{% for post in site.posts %}
  <article>
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
    <p>{{ post.excerpt | strip_html | truncate: 200 }}</p>
  </article>
{% endfor %}
