---
layout: default
title: "weblog"
---

# Latest posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <small>{{ post.date | date: "%Y-%m-%d" }}</small>
      
      <!-- Show the author's name if it's provided -->
      {% if post.author %}
        <p>by {{ post.author }}</p>
      {% endif %}
      
      <p>{{ post.excerpt | truncatewords: 20 }}</p> <!-- Show first 20 words of the excerpt -->
    </li>
  {% endfor %}
</ul>
