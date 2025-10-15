---
layout: archive
title: "Limitless Collection"
permalink: /limitless/
---

<div class="limitless-grid">
  {% for item in site.limitless %}
    {% unless item.title == "Limitless Collection" %}
    <div class="limitless-card">
      <h3><a href="{{ item.url }}">{{ item.title }}</a></h3>
      {% if item.excerpt %}
        <p class="limitless-excerpt">{{ item.excerpt | strip_html | truncate: 150 }}</p>
      {% endif %}
      <div class="limitless-meta">
        <span class="limitless-date">{{ item.date | date: "%B %d, %Y" }}</span>
      </div>
    </div>
    {% endunless %}
  {% endfor %}
</div>

<style>
.limitless-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  padding: 2rem 0;
}

.limitless-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 1.5rem;
  background: #fff;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.limitless-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.15);
}

.limitless-card h3 {
  margin: 0 0 1rem 0;
  font-size: 1.2em;
}

.limitless-card h3 a {
  color: #333;
  text-decoration: none;
}

.limitless-card h3 a:hover {
  color: #0066cc;
  text-decoration: underline;
}

.limitless-excerpt {
  color: #666;
  font-size: 0.9em;
  line-height: 1.5;
  margin-bottom: 1rem;
}

.limitless-meta {
  border-top: 1px solid #eee;
  padding-top: 0.5rem;
}

.limitless-date {
  color: #999;
  font-size: 0.8em;
}
</style>
