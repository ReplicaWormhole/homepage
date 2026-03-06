---
layout: single
title: Blog
permalink: /blog/
---

{% if site.posts.size == 0 %}
No posts yet.
{% else %}
{% for post in site.posts %}
- {{ post.date | date: "%Y-%m-%d" }} — [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}
{% endif %}
