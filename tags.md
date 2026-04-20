---
layout: default
title: Tags
permalink: /tags/
---

<div class="content-body">
  <main class="main-content">
    <div class="page-heading">All Tags</div>
    <div class="tags-page-cloud">
      {% assign all_tags = site.posts | map: "tags" | join: "," | split: "," | uniq | sort %}
      {% for tag in all_tags %}
      <a href="#{{ tag }}" class="tag">{{ tag }}</a>
      {% endfor %}
    </div>

    {% assign all_tags = site.posts | map: "tags" | join: "," | split: "," | uniq | sort %}
    {% for tag in all_tags %}
    <div id="{{ tag }}" style="margin-top:36px;">
      <div class="archive-year">{{ tag }}</div>
      <ul class="archive-list">
        {% for post in site.posts %}
          {% if post.tags contains tag %}
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
