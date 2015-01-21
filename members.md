---
layout: page
title: Members
permalink: /members.html
---
- .
{:toc}

{% for member in site.data.members | sort:"name" %} 

# {{ member.name }}
{:id="{{ member.name | uri_escape }}"}

GitHub: [{{member.github}}](http://www.github.com/{{member.github}}/)
{% if member.homepage != null %}<br/>Web: <{{member.homepage}}>{% endif %}
  
{% assign post_list = site.posts | where:"author", member.name } %}  
{% if post_list.size > 0 %}
{% for post in post_list %}
* [{{post.title}}]({{ root_url }}{{ post.url }}){% endfor %}
{% endif %}

{% endfor %}

