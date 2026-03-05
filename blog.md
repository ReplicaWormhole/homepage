---
layout: single
title: Blog
permalink: /blog/
---

{% assign visible_posts = site.posts | where_exp: "post", "post.show_in_blog != false" %}

{% if visible_posts.size == 0 %}
No posts yet.
{% else %}
{% for post in visible_posts %}
- {{ post.date | date: "%Y-%m-%d" }} — [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}
{% endif %}
