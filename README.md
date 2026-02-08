
# Hi! I'm KJ
## I love computational biology, and like to write in my free time. 

Find out what i'm up to!

---

## Some cool stuff:

{% for post in site.posts limit:5 %}
<div style="background:#f2dce7; border-left:4px solid #c47289; padding:10px; margin-bottom:15px; border-radius:4px;">
  <a href="{{ post.url }}" style="color:#344a32; font-weight:bold; font-size:16px; text-decoration:none;">
    {{ post.title }}
  </a>
  <p style="color:#232323; margin:5px 0;">
    {{ post.excerpt | strip_html | truncate: 150 }}
  </p>
  <small style="color:#9e4f65;">{{ post.date | date: "%b %d, %Y" }}</small>
</div>
{% endfor %}

<p style="margin-top:20px;">
  <a href="/blog" style="color:#c47289; font-weight:bold;">See all posts →</a>
</p>
