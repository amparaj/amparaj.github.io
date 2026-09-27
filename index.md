---
layout: default
title: Home
---

<section class="intro">
  <h1>Hi, I'm Ash.</h1>
  <p>I'm a transport modeller and analyst based in Brisbane, Australia. I work with Python, data analysis, GIS and transport models. I use this site to write up things I've learned and to share side projects.</p>
</section>

<section>
  <h2 class="section-heading">Featured project</h2>
  {% assign featured = site.data.projects | where: "featured", true %}
  {% for project in featured %}
    {% include project-card.html project=project %}
  {% endfor %}
  <p class="more"><a href="{{ "/projects/" | relative_url }}">All projects &rarr;</a></p>
</section>

<section>
  <h2 class="section-heading">Writing</h2>
  <ul class="post-list">
    {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%-d %b %Y" }}</time>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    </li>
    {% endfor %}
  </ul>
</section>
