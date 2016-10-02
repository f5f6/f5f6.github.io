---
layout: page
title: Monthly
permalink: /monthly/
---

<div id="blog-archives">
{% for post in site.categories.monthly %}
{% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
{% unless year == this_year %}
  {% assign year = this_year %}
  <h2>{{ year }}</h2>
{% endunless %}
<article>
  {% include archive_post.html %}
</article>
{% endfor %}
</div>
