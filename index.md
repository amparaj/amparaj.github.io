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
      <p>{{ post.excerpt | truncatewords: 20 }}</p> <!-- Show first 20 words -->
    </li>
  {% endfor %}
</ul>
