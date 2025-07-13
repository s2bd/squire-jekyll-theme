---
layout: default
title: Archive of Chronicles
permalink: /archive/
---

<div class="card">
  <h1>Archive of Chronicles</h1>
  <p class="lead">A complete collection of all tales and wisdom shared within these digital halls, organized by the passage of time.</p>

  {% if site.posts.size > 0 %}
    {% assign posts_by_year = site.posts | group_by_exp: 'post', 'post.date | date: "%Y"' %}
    
    {% for year_group in posts_by_year %}
      <section class="year-section">
        <h2 class="year-heading">{{ year_group.name }}</h2>
        
        {% assign posts_by_month = year_group.items | group_by_exp: 'post', 'post.date | date: "%B"' %}
        
        {% for month_group in posts_by_month %}
          <div class="month-section">
            <h3 class="month-heading">{{ month_group.name }}</h3>
            
            <div class="posts-list">
              {% for post in month_group.items %}
                <article class="archive-post">
                  <header class="archive-post-header">
                    <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
                    <time class="archive-date" datetime="{{ post.date | date_to_xmlschema }}">
                      {{ post.date | date: "%B %d" }}
                    </time>
                  </header>
                  {% if post.excerpt %}
                  <div class="archive-excerpt">
                    {{ post.excerpt | strip_html | truncatewords: 25 }}
                  </div>
                  {% endif %}
                </article>
              {% endfor %}
            </div>
          </div>
        {% endfor %}
      </section>
    {% endfor %}
  {% else %}
    <div class="no-posts">
      <h3>The Archive Awaits</h3>
      <p>No chronicles have been recorded yet. The first entry awaits your noble pen.</p>
    </div>
  {% endif %}
</div>

<style>
.year-section {
  margin-bottom: var(--space-3xl);
}

.year-heading {
  color: var(--burgundy);
  border-bottom: 3px solid var(--gold-primary);
  padding-bottom: var(--space-sm);
  margin-bottom: var(--space-xl);
  position: relative;
}

.year-heading::before {
  content: '📜';
  margin-right: var(--space-sm);
  color: var(--gold-primary);
}

.month-section {
  margin-bottom: var(--space-2xl);
}

.month-heading {
  color: var(--ink-medium);
  font-size: var(--font-size-xl);
  margin-bottom: var(--space-lg);
  padding-left: var(--space-lg);
  border-left: 4px solid var(--gold-primary);
}

.posts-list {
  margin-left: var(--space-xl);
}

.archive-post {
  background: rgba(255, 255, 255, 0.5);
  border: 1px solid rgba(212, 175, 55, 0.2);
  border-radius: var(--radius-md);
  padding: var(--space-lg);
  margin-bottom: var(--space-lg);
  transition: var(--transition-normal);
}

.archive-post:hover {
  background: rgba(255, 255, 255, 0.8);
  border-color: var(--gold-primary);
  transform: translateX(var(--space-sm));
}

.archive-post-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: var(--space-sm);
  gap: var(--space-lg);
}

.archive-post h4 {
  margin: 0;
  font-size: var(--font-size-lg);
  flex: 1;
}

.archive-post h4 a {
  color: var(--ink-dark);
  text-decoration: none;
  border: none;
}

.archive-post h4 a:hover {
  color: var(--burgundy);
}

.archive-date {
  color: var(--ink-light);
  font-size: var(--font-size-sm);
  font-family: 'Open Sans', sans-serif;
  font-weight: 600;
  white-space: nowrap;
  background: rgba(212, 175, 55, 0.1);
  padding: var(--space-xs) var(--space-sm);
  border-radius: var(--radius-sm);
}

.archive-excerpt {
  color: var(--ink-medium);
  font-size: var(--font-size-base);
  line-height: 1.5;
  margin-top: var(--space-sm);
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

@media (max-width: 768px) {
  .archive-post-header {
    flex-direction: column;
    align-items: flex-start;
    gap: var(--space-sm);
  }
  
  .posts-list {
    margin-left: 0;
  }
  
  .month-heading {
    padding-left: var(--space-sm);
  }
}
</style>