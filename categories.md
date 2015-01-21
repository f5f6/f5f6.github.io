---
layout: page
title: Categories
permalink: /categories/
---
{% for category in site.categories %} 

<h2 id='{{ category[0] | uri_escape }}' style="margin-top: 2.5rem;">{{ category[0] | upcase}}</h2>

<div id="blog-archives">
 {% assign pages_list = category[1] reverse %}
  {% for post in pages_list %}
{% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
{% unless year == this_year %}
  {% assign year = this_year %}
  <h2>{{ year }}</h2>
{% endunless %}
<article>
  {% capture category %}{{ post.categories | size }}{% endcapture %}
<h1><a href="{{ root_url }}{{ post.url }}">{{post.title}}</a></h1>
<time datetime="{{ post.date | datetime | date_to_xmlschema }}" pubdate>{{ post.date | date: "<span class='month'>%b</span> <span class='day'>%d</span> <span class='year'>%Y</span>"}}</time>
</article>
{% endfor %}
</div>
{% endfor %}

