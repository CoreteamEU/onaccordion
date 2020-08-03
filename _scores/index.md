---
title: "Free sheet music"
layout: default
date: 2020-06-26 01:10:01 +0300
pagination:
  enabled: true
  collection: scores
---

{% if page.title %}

  <h1 class="page-heading">{{ page.title }}</h1>
{% endif %}

{% if site.scores.size > 0 %}

  <h2 class="post-list-heading">{{ page.list_title | default: "" }}</h2>
  <ul class="post-list">
    {% for post in site.scores reversed %}
      {% if post.tags contains "score" %}
        <li>
          <!-- {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %} -->
          <!-- <span class="post-meta">{{ post.date | date: date_format }}</span> -->
          <h4>
            <a  href="{{ post.url | relative_url }}">
              {{ post.artist }} - {{ post.title }}
            </a>
|
            <a href="{{ post.folder }}/{{ post.pdf_url | escape }}">
              <span class="icon icon-download"></span>
            </a>
  
          </h4>
          {% if site.show_excerpts %}
            {{ post.excerpt }}
          {% endif %}
        </li>
      {% endif %}
    {% endfor %}

  </ul>
  {% endif %}
