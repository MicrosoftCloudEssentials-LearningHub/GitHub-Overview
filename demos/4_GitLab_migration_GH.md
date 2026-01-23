# From GitLab to GitHub - Overview 

Costa Rica

[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/) [brown9804](https://github.com/brown9804)

Last updated: 2025-10-07

----------------------

> Migrating a repository from GitLab to GitHub involves exporting your code and history, setting up a new GitHub repository, and carefully transferring issues, CI/CD pipelines, and permissions. The process is straightforward for code but requires extra steps for workflows and collaboration data.

<details>
<summary><b>List of References </b> (Click to expand)</summary>

- [Repository limits GH](https://docs.github.com/en/repositories/creating-and-managing-repositories/repository-limits)
- [Planning your migration to GitHub](https://docs.github.com/en/migrations/overview/planning-your-migration-to-github)

</details>

| Aspect              | GitLab → GitHub Migration Notes |
|---------------------|---------------------------------|
| **Code & History**  | Easy with `git clone --mirror` and `git push --mirror`. |
| **Issues**          | Requires API tools or manual import; labels may need rework. |
| **CI/CD**           | Pipelines must be rewritten for GitHub Actions. |
| **Wiki**            | Can be cloned/pushed separately as another repo. |
| **Permissions**     | Must be recreated manually in GitHub. |
| **Integrations**    | GitHub offers broader ecosystem (Actions, Copilot, Codespaces). |


> [!NOTE]
> Preparation:
> - Audit your GitLab repo: Check branches, tags, issues, merge requests, and CI/CD pipelines.
> - Decide scope: Are you migrating just the code, or also issues, wiki, and pipelines?
> - Access setup: Ensure you have admin rights on both GitLab and GitHub.


## Repository Migration (Code + History)

1. Clone your GitLab repository:
   ```bash
   git clone --mirror https://gitlab.com/username/repo.git
   ```
   - `--mirror` ensures all branches, tags, and refs are included.
2. Create a new repository on GitHub (empty).
3. Push the mirrored repo to GitHub:
   ```bash
   cd repo.git
   git push --mirror https://github.com/username/repo.git
   ```

> At this point, your code and commit history are fully migrated.

## Issues and Comments

> [!NOTE]
> Some metadata (labels, assignees) may need manual adjustment.

- GitHub does not natively import GitLab issues.
- Options:
  - **Third-party tools**: e.g., *gitlab2github* or *Python scripts* that use GitLab/GitHub APIs.
  - **Manual export/import**: Export issues from GitLab as JSON/CSV, then use GitHub’s API to recreate them.

## CI/CD Pipelines

- GitLab CI uses `.gitlab-ci.yml`; GitHub uses **GitHub Actions** (`.github/workflows/*.yml`).
- Migration requires **rewriting pipeline definitions**:
  - Map GitLab jobs to GitHub Actions workflows.
  - Replace GitLab-specific runners with GitHub-hosted runners.
- Test workflows thoroughly after migration.

## Permissions and Collaboration

- Recreate teams and permissions in GitHub.
- GitHub offers **Organizations, Teams, and Role-based access control**.
- If migrating multiple repos, consider using **GitHub Enterprise migration tools**.


<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-1289-limegreen" alt="Total views">
  <p>Refresh Date: 2025-10-07</p>
</div>
<!-- END BADGE -->
