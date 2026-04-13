---
layout: default
title: Blog
---
<img 
  src="https://raw.githubusercontent.com/yourusername/yourrepo/output/github-contribution-grid-snake.svg" 
  alt="GitHub Snake"
  style="width:100%; max-width:700px;"
/>
## Blog

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%b %d, %Y" }}
{% endfor %}

<!-- not working since --- used every time smth is closed -->
[← Back to Home](/)
