---
layout: page
title: Categories
permalink: /categories/
---

{% for category in site.categories %} 
  <h1 id='{{ category[0] }}-ref'>{{ category[0] }}</h1>
  <ul>
  {% assign pages_list = category[1] %}  
 	{% for post in pages_list %}
    {% if post.title != null %}
      	<li class="related-posts"><a href="{{ BASE_PATH }}{{post.url}}">{{post.title}}</a>  -- <time datetime="{{ post.date | datetime | date_to_xmlschema }}" pubdate>{{ post.date | date: "<span class='month'>%b</span> <span class='day'>%d</span> <span class='year'>%Y</span>"}}</time></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}

