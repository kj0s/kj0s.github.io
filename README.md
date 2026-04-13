
# Hi! I'm KJ
## I love computational biology, and like to write in my free time. 

---

## Contributions 
<img 
  src="https://raw.githubusercontent.com/yourusername/yourrepo/output/github-contribution-grid-snake.svg" 
  alt="GitHub Snake"
  style="width:100%; max-width:700px;"
/>

---

## Some cool stuff:

---
### Recent Code

<div id="repo-list"></div>

<script>
const username = "kj0s";

fetch(`https://api.github.com/users/${username}/repos`)
  .then(res => res.json())
  .then(repos => {
    const container = document.getElementById("repo-list");

    repos = repos
      .filter(repo => !repo.fork)
      .sort((a, b) => new Date(b.updated_at) - new Date(a.updated_at))
      .slice(0, 4);

    repos.forEach(repo => {
      const el = document.createElement("div");
      el.className = "card";

      el.innerHTML = `
        <a href="${repo.html_url}" target="_blank">
          ${repo.name}
        </a>
        <p>
          ${repo.description || "No description provided."}
        </p>
        <small>
          ⭐ ${repo.stargazers_count} | Updated: ${new Date(repo.updated_at).toLocaleDateString()}
        </small>
      `;

      container.appendChild(el);
    });
  });
</script>

---
### Posts and Writing!
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
