---
layout: page
title: ARCHIVE
permalink: /posts/
---



<div class="tag-filter-menu">
  <button class="filter-btn active" data-filter="all">ALL</button>

  {% for tag in site.tags %}
    {% assign tag_name = tag | first %}
    <button class="filter-btn" data-filter="{{ tag_name | downcase }}">{{ tag_name | upcase }}</button>
  {% endfor %}
</div>

<div class="post-grid">
  {% for post in site.posts %}
    {% assign primary_tag = post.tags | first | slugify %}

    <article class="post-card tag-{{ primary_tag }}" data-tags="{{ post.tags | join: ' ' | downcase }}">
      <div class="post-card-visual">
        <div class="tag-letters">
          {% for tag in post.tags %}
            {% assign tag_slug = tag | slugify %}
            <span class="tag-char">
              {% case tag_slug %}
                {% when 'urban-studies' %}URBANISME
                {% when 'urbanstudies' %}URBANISME
                {% when 'politics' %}POL
                {% when 'sociology' %}SOCIO
                {% when 'history' %}HIST
                {% when 'economics' %}ÉCON
                {% when 'data-visualisation' %}DATAVIZ
                {% when 'datavisualisation' %}DATAVIZ
                {% when 'data' %}DATA
                {% when 'casual' %}NOTES
                {% when 'astrology' %}ASTRO
                {% when 'football' %}FTBL
                {% else %}{{ tag | upcase }}
              {% endcase %}
            </span>
          {% endfor %}
        </div>
      </div>

      <div class="post-card-content">
        <div class="details">{{ post.date | date: '%Y %b %d' }}</div>
        <h2 class="title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p class="excerpt">{{ post.excerpt | strip_html | truncatewords: 15 }}</p>

        <div class="post-tags-row">
          {% for tag in post.tags %}
            <span class="mini-tag">#{{ tag }}</span>
          {% endfor %}
        </div>
      </div>
    </article>
  {% endfor %}
</div>



<script>
document.addEventListener('DOMContentLoaded', function() {
  const buttons = document.querySelectorAll('.filter-btn');
  const posts = document.querySelectorAll('.post-card');

  buttons.forEach(button => {
    button.addEventListener('click', () => {
      // 1. Remove the 'active' black background from all buttons
      buttons.forEach(btn => btn.classList.remove('active'));

      // 2. Add the 'active' background to the one you just clicked
      button.classList.add('active');

      // 3. Find out which tag we are filtering by
      const filterValue = button.getAttribute('data-filter');

      // 4. Loop through all posts and hide/show them
      posts.forEach(post => {
        if (filterValue === 'all') {
          post.style.display = 'flex'; // Show everything
        } else {
          // Check if the post's hidden data-tags includes our filter
          const postTags = post.getAttribute('data-tags');
          if (postTags.includes(filterValue)) {
            post.style.display = 'flex'; // Show it
          } else {
            post.style.display = 'none'; // Hide it
          }
        }
      });
    });
  });
});
</script>
