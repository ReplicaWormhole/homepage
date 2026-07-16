---
layout: single
title: Practice
permalink: /blog/practice/
---

Side projects, code, tutorials, and computational experiments.

{% assign posts = site.posts | where: "section", "practice" %}
{% if posts.size == 0 %}
No practice posts yet.
{% else %}
{% for post in posts %}
- {{ post.date | date: "%Y-%m-%d" }} — [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}
{% endif %}

[All blog posts]({{ '/blog/' | relative_url }})
