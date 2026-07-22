---
layout: default
title: ARCHIVE
permalink: /posts/
---


<div>
  {% for post in site.posts %}
    {% assign primary_tag = post.tags | first | slugify %}


      <div>
        <div>{{ post.date | date: '%Y %b %d' }}</div>
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p>{{ post.excerpt | strip_html | truncatewords: 15 }}</p>

        <div>
          {% for tag in post.tags %}
            <span>#{{ tag }}</span>
          {% endfor %}
        </div>
      </div>
  {% endfor %}
</div>



