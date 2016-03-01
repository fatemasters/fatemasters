---
layout: page
show_meta: false
title: "Podcasts do Fate Masters"
header:
    image_fullwidth: FundoBlog.png
permalink: "/podcast/"
---
<ul>
    {% for post in site.categories.podcast %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

<ul>
