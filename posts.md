---
layout: base
title: Posts
---

I plan to list all posts here.

{% for post in site.posts %}

- [{{ post.title }}]({{ post.url }})

{% endfor %}