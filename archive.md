---
layout: page
title: Archive
permalink: /archive/
---

## Blog Posts

{% for post in site.categories.posts %}
  * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}