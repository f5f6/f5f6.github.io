---
layout: page
title: Members
permalink: /members/
---

{% for member in site.data.members %} 
  <h1 id='{{ member.name }}-ref'>{{ member.name }}</h1>
  **Profiles:** <a href="http://www.github.com/{{member.github}}/">Github</a>{% if member.homepage != null %} | <a href="{{member.homepage}}">Home Page</a>{% endif %}
  
 {% assign post_list = site.posts | where:"author", member.name } %}  
 {% if post_list.size > 0 %}
 **Posts:**
 {% for post in post_list %}

<a href="{{ root_url }}{{ post.url }}">{{post.title}}</a> -- <time datetime="{{ post.date | datetime | date_to_xmlschema }}" pubdate>{{ post.date | date: "<span class='month'>%b</span> <span class='day'>%d</span> <span class='year'>%Y</span>"}}</time>

 {% endfor %}

  {% endif %}
{% endfor %}

