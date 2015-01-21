---
layout: page
title: Members
permalink: /members/
---
- .
{:toc}

{% for member in site.data.members | sort:"name" %} 

# {{ member.name }}
{:id="{{ member.name | uri_escape }}"}

GitHub: [{{member.github}}](http://www.github.com/{{member.github}}/)
{% for link in member.links %}|
{% if link.type %}{{ link.type | capitalize }}: {% endif %}{% if link.name %}[{{link.name}}]({{link.url}}){% else %}<{{link.url}}>{% endif %} {% endfor %} 

{% if member.description %}{{ member.description }}{% endif %}
  
{% assign post_list = site.posts | where:"author", member.name } %}  
{% if post_list.size > 0 %}
{% for post in post_list %}
* [{{post.title}}]({{ root_url }}{{ post.url }}){% endfor %}
{% endif %}

{% endfor %}

