---
layout: page
title: Flashcards
permalink: /flashcards/
---
<h3>Themen</h3>
<ul>
{% for post in site.pages %}
    {% if post.layout == "flashcards" %}
        
        <li><a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
{% endfor %}
</ul>

