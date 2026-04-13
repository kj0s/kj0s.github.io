## Code 
<div id="repo-list"></div>

<script>
const username = "kj0s";

fetch(`https://api.github.com/users/${username}/repos`)
  .then(response => response.json())
  .then(repos => {
    const container = document.getElementById("repo-list");

    // sort by most recently updated
    repos.sort((a, b) => new Date(b.updated_at) - new Date(a.updated_at));

    repos.forEach(repo => {
      const repoEl = document.createElement("div");
      repoEl.className = "repo-card";

      repoEl.innerHTML = `
        <h3><a href="${repo.html_url}" target="_blank">${repo.name}</a></h3>
        <p>${repo.description || "No description provided."}</p>
        <small>
          ⭐ ${repo.stargazers_count} | 
          🍴 ${repo.forks_count}
        </small>
      `;

      container.appendChild(repoEl);
    });
  })
  .catch(err => console.error(err));
</script>
<!-- not working since --- used every time smth is closed -->
[← Back to Home](/)
