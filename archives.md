---
layout: default
title: Archives
permalink: /archives/
---

<div class="content-body">
  <main class="main-content">
    <div class="page-heading">Archives</div>

    {% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
    {% for year in postsByYear %}
    <div class="archive-year">{{ year.name }}</div>
    <ul class="archive-list">
      {% for post in year.items %}
      <li>
        <span class="arc-date">{{ post.date | date: "%b %d" }}</span>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
      {% endfor %}
    </ul>
    {% endfor %}
  </main>
  {% include right-sidebar.html %}
</div>
