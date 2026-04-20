---
layout: default
title: Categories
permalink: /categories/
---

<div class="content-body">
  <main class="main-content">
    <div class="page-heading">Categories</div>

    {% assign all_cats = site.posts | map: "platform" | uniq | sort %}
    {% for cat in all_cats %}
    <div style="margin-top:28px;">
      <div class="archive-year">{{ cat }}</div>
      <ul class="archive-list">
        {% for post in site.posts %}
          {% if post.platform == cat %}
          <li>
            <span class="arc-date">{{ post.date | date: "%b %d, %Y" }}</span>
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </li>
          {% endif %}
        {% endfor %}
      </ul>
    </div>
    {% endfor %}
  </main>
  {% include right-sidebar.html %}
</div>
