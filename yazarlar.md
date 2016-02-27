---
layout: page
title: Yazarlar
---

<div class="posts">
{% for author in site.authors %}
  <a name="{{ author[1].name }}"></a>
  <h3>{{ author[1].display_name }}</h3>
  <ol>

    {% for post in site.posts %}
    {% if post.author == author[1].name %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
    {% endfor %}

  </ol>
{% endfor %}
</div>
