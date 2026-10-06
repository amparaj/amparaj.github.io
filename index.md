---
layout: default
title: Home
---

<section class="intro">
  <h1>Hi, I'm Ash.</h1>
  <p>I'm a travel demand modeller based in Brisbane, Australia, with a focus on strategic transport demand, urban transport and economics. My daily work involves developing and maintaining complex transport models to inform planning and economic policy decisions, as well as to solve infrastructure challenges. Outside work, I'm passionate about analytics and modelling to help solve whatever problem catches my interest, from spatial and economic questions to forecasting Formula 1 races and predicting player points in Fantasy Premier League. I use this site to write up my technical learnings and share my side projects.</p>
</section>

<section>
  <h2 class="section-heading">Featured projects</h2>
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
