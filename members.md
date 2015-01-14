---
layout: page
title: Members
permalink: /members.html
---

{% assign members = site.data.members | sort:"name" %}

{% for member in  members %} 
  <h1 id='{{ member.name }}-ref'>{{ member.name }}</h1>
  **Profile:** <a href="http://www.github.com/{{member.github}}/">Github</a>{% if member.homepage != null %} | <a href="{{member.homepage}}">Home Page</a>{% endif %}
  
 {% assign post_list = site.posts | where:"author", member.name } %}  
 {% if post_list.size > 0 %}
 **Posts:**

<ul class="related-posts">
  {% for post in post_list %}
<li><a href="{{ root_url }}{{ post.url }}">{{post.title}}</a> -- <time datetime="{{ post.date | datetime | date_to_xmlschema }}" pubdate>{{ post.date | date: "<span class='month'>%b</span> <span class='day'>%d</span> <span class='year'>%Y</span>"}}</time></li>
  {% endfor %}
</ul>
  {% endif %}
{% endfor %}

