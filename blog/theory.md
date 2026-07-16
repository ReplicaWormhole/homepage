---
layout: single
title: Theory
permalink: /blog/theory/
---

Informal notes on mathematics, physics and computer science.

{% assign posts = site.posts | where: "section", "theory" %}
{% if posts.size == 0 %}
No theory notes yet.
{% else %}
{% for post in posts %}
- {{ post.date | date: "%Y-%m-%d" }} — [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}
{% endif %}

[All blog posts]({{ '/blog/' | relative_url }})
