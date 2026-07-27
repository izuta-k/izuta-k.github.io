---
layout: default
title: ARCHIVE
permalink: /posts/
---


<div class="postlist">
  {% for post in site.posts %}

      <div class="poststrip">
        <div class="postlistdate">{{ post.date | date: '%Y %b %d' }}</div>
        <div class="post-content">
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>

        <div class="posttag">
          {% for tag in post.tags %}
            <span>#{{ tag | slugify }}</span>
          {% endfor %}
      </div>
          
        </div>
      </div>
  {% endfor %}
</div>



