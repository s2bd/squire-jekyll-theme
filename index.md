---
layout: default
title: Home
---

<div class="card">
  <div class="hero-section">
    <h1 class="hero-title">{{ site.title }}</h1>
    <p class="hero-subtitle lead">{{ site.description }}</p>
    <p>Welcome to a realm where words carry the weight of kingdoms and stories unfold like ancient scrolls. Here, every article is crafted with the precision of a master scribe and the passion of a noble quest.</p>
  </div>

  <div class="posts-section">
    <h2>Chronicles & Tales</h2>

    {% if site.posts.size > 0 %}
      {% for post in site.posts limit: 5 %}
        <article class="post-preview">
          <header>
            <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
            <div class="post-meta">
              <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
              {% if post.author %}
              <span class="author">by {{ post.author }}</span>
              {% endif %}
            </div>
          </header>
          <div class="post-excerpt">
            {{ post.excerpt | strip_html | truncatewords: 50 }}
          </div>
          <footer>
            <a href="{{ post.url | relative_url }}" class="read-more">Continue Reading →</a>
          </footer>
        </article>
      {% endfor %}
      
      {% if site.posts.size > 5 %}
      <div class="text-center mt-2xl">
        <a href="{{ '/archive' | relative_url }}" class="view-all-posts">View All Chronicles →</a>
      </div>
      {% endif %}
    {% else %}
      <div class="no-posts">
        <h3>The Chronicles Await</h3>
        <p>No tales have been penned yet. The first story awaits your noble hand.</p>
      </div>
    {% endif %}
  </div>
</div>

<style>
.post-excerpt {
  margin: var(--space-lg) 0;
  color: var(--ink-medium);
  line-height: 1.6;
}

.read-more {
  color: var(--burgundy);
  font-weight: 600;
  text-decoration: none;
  font-family: 'Open Sans', sans-serif;
  font-size: var(--font-size-base);
  transition: var(--transition-normal);
}

.read-more:hover {
  color: var(--burgundy-light);
  border-bottom-color: var(--gold-primary);
}

.view-all-posts {
  display: inline-block;
  background: linear-gradient(135deg, var(--gold-primary), var(--gold-secondary));
  color: var(--ink-dark);
  padding: var(--space-lg) var(--space-2xl);
  border-radius: var(--radius-md);
  text-decoration: none;
  font-weight: 700;
  font-family: 'Open Sans', sans-serif;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  transition: var(--transition-normal);
  box-shadow: 0 4px 15px var(--shadow-light);
  border: none;
}

.view-all-posts:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px var(--shadow-medium);
  border: none;
}

.no-posts {
  text-align: center;
  padding: var(--space-3xl);
  color: var(--ink-light);
}

.no-posts h3 {
  color: var(--ink-medium);
  margin-bottom: var(--space-lg);
}
</style>