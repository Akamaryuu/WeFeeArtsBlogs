---
layout: default
title: 連載
permalink: /series/
---

# 連載

{% for s in site.series %}
<section class="series-block" id="{{ s.slug }}">
  <h2>{{ s.name }}</h2>
  <p>{{ s.description }}</p>
  <ul>
    {% assign posts = site.posts | where_exp: "p", "p.categories.first == s.slug" %}
    {% for post in posts %}
    <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> <small>（{{ post.date | date: "%Y-%m-%d" }}）</small></li>
    {% endfor %}
    {% if posts.size == 0 %}<li>まだ記事がありません。</li>{% endif %}
  </ul>
</section>
{% endfor %}
