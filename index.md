---
layout: default
title: "weblog"
---

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <small>{{ post.date | date: "%Y-%m-%d" }}</small>
      <p>{{ post.excerpt | truncatewords: 20 }}</p> <!-- Shows first 20 words as a preview -->
    </li>
  {% endfor %}
</ul>