---
layout: single
title: Musings
permalink: /blog/musings/
---

Here I collect musings on topics I care about.

{% assign posts = site.posts | where: "section", "musings" %}
{% if posts.size == 0 %}
No musings yet.
{% else %}
{% for post in posts %}
- {{ post.date | date: "%Y-%m-%d" }} — [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}
{% endif %}

[All blog posts]({{ '/blog/' | relative_url }})
