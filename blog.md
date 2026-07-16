---
layout: single
title: Blog
permalink: /blog/
---

Notes, projects, and occasional observations. This is a place to informally share thoughts and ideas more freely than appropriate for academic papers.
The aim is not to be correct but to be a representation of my thoughts in the moment. As my thoughts develop over time, posts will repeat topics and represent a snapshot of my perspective at the time of their writing.

- [Theory]({{ '/blog/theory/' | relative_url }}) — informal notes on mathematics and physics.
- [Practice]({{ '/blog/practice/' | relative_url }}) — side projects, code, tutorials, and computational experiments.
- [Musings]({{ '/blog/musings/' | relative_url }}) — thoughts and observations on science, technology, and other things.

## Recent posts

{% if site.posts.size == 0 %}
No posts yet.
{% else %}
{% for post in site.posts %}
- {{ post.date | date: "%Y-%m-%d" }} — [{{ post.title }}]({{ post.url | relative_url }}){% if post.section %} · {{ post.section | capitalize }}{% endif %}
{% endfor %}
{% endif %}
