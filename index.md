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

  <table>
    {% for post in site.scores %}
      {% if post.tags contains "score" %}
        <tr>
          <td>
            <a  href="{{ post.url | relative_url }}">
              {{ post.artist }} - {{ post.title }}
            </a>
          </td>
          <td>
            <a href="scores/{{ post.folder }}/{{ post.pdf_url | escape }}">
              Download sheet <span class="icon icon-download"></span>
            </a>
          </td>
          <td>
            {% if post.youtube %}
              <a href="{{ post.youtube }}"> Watch on Youtube </a>
            {% endif %}
          </td>
        </tr>
      {% endif %}
    {% endfor %}
  </table>

{% endif %}

  <h1 class="page-heading">About</h1>
  More on this site [here](/about)
