---
layout: default
title: Research
tag: research
permalink: /tags/research/
---

<h2>Posts tagged: {{ page.tag | capitalize }}</h2>
<hr>

{% assign tag_name = page.tag %}
{% assign tagged_posts = site.posts | where_exp: "post", "post.tags contains tag_name" %}
{% for post in tagged_posts %}
  <div class="mb-4">
    <h4><a href="{{ post.url }}">{{ post.title }}</a></h4>
    <p><small>{{ post.date | date: "%B %d, %Y" }}</small></p>
    <p>{{ post.excerpt }}</p>
    <hr>
  </div>
{% endfor %}
