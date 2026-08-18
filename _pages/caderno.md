---
title: "Caderno"
permalink: /caderno/
excerpt: "Notas, chamadas e notícias da comunidade."
---

<p class="sb-page-lead">
  O lado editorial do projeto: notas curtas sobre organização, divulgação e
  circulação de seminários no Brasil.
</p>

{% for post in site.posts %}
<article class="archive__item">
  <p class="page__meta">
    <span>{{ post.date | date: "%d/%m/%Y" }}</span>
    {% if post.category %} · <span>{{ post.category }}</span>{% endif %}
  </p>
  <h2 class="archive__item-title">
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </h2>
  <p class="archive__item-excerpt">{{ post.excerpt | strip_html }}</p>
</article>
{% endfor %}
