---
layout: default
title: RESEARCH
permalink: /research/
---

<div>
  {% assign research_groups = site.research | group_by: 'type' %}
  
  {% for group in research_groups %}
    <h2>{{ group.name | upcase }}S</h2>
    
    <div>
      {% for item in group.items %}
        <article>
          <div >
            <div>{{ item.date | date: "%Y" }}</div>
            <h2>
              <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
            </h2>
            <p>{{ item.excerpt }}</p>
            <div>
              <span>#{{ item.type | lowercase }}</span>
            </div>
          </div>
        </article>
      {% endfor %}
    </div>
  {% endfor %}
</div>
