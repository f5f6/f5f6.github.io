---
layout: page
title: Categories
permalink: /categories/
---

{% for category in site.categories %} 
  <h1 id='{{ category[0] }}-ref'>{{ category[0] }}</h1>
  <ul>
  {% assign pages_list = category[1] %}  
 	{% for node in pages_list %}
    {% if node.title != null %}
      	<li class="related-posts"><a href="{{ BASE_PATH }}{{node.url}}">{{node.title}}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}

