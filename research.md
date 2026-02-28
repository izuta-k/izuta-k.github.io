---
layout: default
title: RESEARCH
permalink: /research/
---

<div class="research-archive">
  {% assign research_groups = site.research | group_by: 'type' %}
  
  {% for group in research_groups %}
    <h2 class="section-divider">{{ group.name | upcase }}S</h2>
    
    <div class="post-grid">
      {% for item in group.items %}
        <article class="post-card">
          <div class="post-card-content">
            <div class="details">{{ item.date | date: "%Y" }}</div>
            <h2 class="title">
              <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
            </h2>
            <p class="excerpt">{{ item.excerpt }}</p>
            <div class="post-tags-row">
              <span class="mini-tag">#{{ item.type | lowercase }}</span>
            </div>
          </div>
        </article>
      {% endfor %}
    </div>
  {% endfor %}
</div>
