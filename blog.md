---
layout: default
title: Blog
---

## Blog

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%b %d, %Y" }}
{% endfor %}

---
<!-- not working since --- used every time smth is closed -->
[← Back to Home](/)

