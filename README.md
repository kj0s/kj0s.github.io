
# Hi! I'm KJ
## I love computational biology, and like to write in my free time. 

---

## Contributions 🐍

<div style="text-align:center; margin-top:20px;">
  <img 
    src="https://raw.githubusercontent.com/yourusername/yourrepo/output/github-contribution-grid-snake.svg" 
    alt="GitHub Snake"
    style="width:100%; max-width:700px;"
  />
</div>

---

## Some cool stuff:

---

## Recent Code

<div id="repo-list"></div>

<script>
const username = "kj0s";

fetch(`https://api.github.com/users/${username}/repos`)
  .then(res => res.json())
  .then(repos => {
    const container = document.getElementById("repo-list");

    // remove forks
    repos = repos.filter(repo => !repo.fork);

    // sort by last updated
    repos.sort((a, b) => new Date(b.updated_at) - new Date(a.updated_at));

    // only show top 4
    repos.slice(0, 4).forEach(repo => {
      const el = document.createElement("div");

      el.style.background = "#f2dce7";
      el.style.borderLeft = "4px solid #c47289";
      el.style.padding = "10px";
      el.style.marginBottom = "15px";
      el.style.borderRadius = "4px";

      el.innerHTML = `
        <a href="${repo.html_url}" target="_blank" 
           style="color:#344a32; font-weight:bold; font-size:16px; text-decoration:none;">
          ${repo.name}
        </a>
        <p style="color:#232323; margin:5px 0;">
          ${repo.description || "No description provided."}
        </p>
        <small style="color:#9e4f65;">
          ⭐ ${repo.stargazers_count} | Updated: ${new Date(repo.updated_at).toLocaleDateString()}
        </small>
      `;

      container.appendChild(el);
    });
  })
  .catch(err => console.error(err));
</script>

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
