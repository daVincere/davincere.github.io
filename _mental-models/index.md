---
layout: archive
title: "Mental Models Collection"
permalink: /mental-models/
---

{% assign sorted_models = site.data.mental_models | sort: "id" %}

<div class="mental-models-grid">
  {% for model in sorted_models %}
    <div class="mental-model-card">
      <div class="mental-model-tag">{{ model.tag }}</div>
      <div class="mental-model-text">
        {{ model.text | markdownify }}
      </div>
      {% if model.link %}
        <div class="mental-model-link">
          <a href="{{ model.link }}" target="_blank">Link →</a>
        </div>
      {% endif %}
      <div class="mental-model-date">{{ model.date | date: "%B %d, %Y" }}</div>
    </div>
  {% endfor %}
</div>

<style>
.mental-models-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  padding: 2rem 0;
}

.mental-model-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 1.5rem;
  background: #fff;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  position: relative;
}

.mental-model-id {
  position: absolute;
  top: 0.5rem;
  right: 0.5rem;
  font-size: 0.8em;
  color: #999;
}

.mental-model-tag {
  color: #666;
  font-size: 0.8em;
  text-transform: uppercase;
  margin-bottom: 0.5rem;
}

.mental-model-text {
  font-size: 1em;
  margin-bottom: 1rem;
}

.mental-model-link a {
  color: #0066cc;
  text-decoration: none;
}

.mental-model-link a:hover {
  text-decoration: underline;
}

.mental-model-date {
  color: #999;
  font-size: 0.8em;
  margin-top: 0.5rem;
}
</style>