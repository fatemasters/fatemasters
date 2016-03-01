---
layout: page
show_meta: false
title: "Quem são os Fate Masters?"
header:
    image_fullwidth: FundoBlog.png
    permalink: "/authors/"
---

Mais informações sobre os algozes dos jogadores e sobre os convidados que participaram do Fate Masters

<ul>
    {% for post in site.authors %}
    <li><a href="{{ post.url }}">{{ post.title | markdownify | remove: '<p>' | remove: '</p>' }}</a></li>
{% comment %}
{{ post.content }}
{% endcomment %}
    {% endfor %}
</ul>

