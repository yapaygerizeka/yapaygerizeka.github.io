---
layout: page
title: Yazarlar
---

<div class="posts">
{% for author in site.authors %}
  {% comment %}
    Sadece postu olan yazarlar gosteriliyor
  {% endcomment %}
  {% assign have_posts = false %}
  {% for post in site.posts %}
    {% if post.author == author[1].name %}
      {% assign have_posts = true %}
    {% endif %}
  {% endfor %}
  {% if have_posts %}
  <a name="{{ author[1].name }}"></a>
  <h3>
    {{ author[1].display_name }}
    <sup>
    {% if author[1].web %}<a href="{{ author[1].web }}" class="author-link"><i class="fa fa-external-link"></i></a>{% endif %}
    {% if author[1].twitter %}<a href="https://twitter.com/{{ author[1].twitter }}" class="author-link"><i class="fa fa-twitter"></i></a>{% endif %}
    {% if author[1].github %}<a href="https://github.com/{{ author[1].github }}" class="author-link"><i class="fa fa-github"></i></a>{% endif %}
    </sup>
  </h3>
  <ol>
    {% for post in site.posts %}
    {% if post.author == author[1].name %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
    {% endfor %}
  </ol>
  {% endif %}
{% endfor %}
</div>
