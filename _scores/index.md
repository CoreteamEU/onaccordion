---
title: "Free sheet music for download"
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
    {% for post in site.scores %}
    {% if post.category != "score" %}
      {% continue %}
    {% endif %}

    <li>
      <!-- {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %} -->
      <!-- <span class="post-meta">{{ post.date | date: date_format }}</span> -->
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      {% if site.show_excerpts %}
        {{ post.excerpt }}
      {% endif %}
    </li>

    {% endfor %}

  </ul>
  {% endif %}
