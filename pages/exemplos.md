---
layout: page
show_meta: false
title: "Exemplos citados no podcast"
header:
    image_fullwidth: FundoBlog.png
permalink: "/exemplos/"
---
<ul>
    {% for post in site.categories.exemplos %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

<ul>
