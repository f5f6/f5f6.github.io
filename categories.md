---
layout: page
title: 日志分类
permalink: /categories/
---

{% for category in site.categories %} 
  <h2 id='{{ category[0] }}-ref'>{{ category[0] }}</h2>
  <ul>
  {% assign pages_list = category[1] %}  
 	{% for node in pages_list %}
    {% if node.title != null %}
      	<li><a href="{{ BASE_PATH }}{{node.url}}">{{node.title}}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}

