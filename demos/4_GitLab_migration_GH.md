# From GitLab to GitHub - Overview 

Costa Rica

[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/) [brown9804](https://github.com/brown9804)

Last updated: 2026-01-25

----------------------

> Migrating a repository from GitLab to GitHub involves exporting your code and history, setting up a new GitHub repository, and carefully transferring issues, CI/CD pipelines, and permissions. The process is straightforward for code but requires extra steps for workflows and collaboration data.

<details>
<summary><b>List of References </b> (Click to expand)</summary>

- [Repository limits GH](https://docs.github.com/en/repositories/creating-and-managing-repositories/repository-limits)
- [Planning your migration to GitHub](https://docs.github.com/en/migrations/overview/planning-your-migration-to-github)
- [About large files on GitHub](https://docs.github.com/en/enterprise-cloud@latest/repositories/working-with-files/managing-large-files/about-large-files-on-github)

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

> E.g Repo of 4.2 GB:

<img width="1912" height="1077" alt="image" src="https://github.com/user-attachments/assets/ffef6d19-ae63-41c8-b5ed-15cf864d5e30" />

https://github.com/user-attachments/assets/5996e84e-f50b-4670-b6e5-de8310421c21

> History example:

https://github.com/user-attachments/assets/fffbbce1-8a48-49f7-a8d8-96da6d9c433e

1. Clone your GitLab repository:

   ```bash
   git clone --mirror https://gitlab.com/username/repo.git
   ```
   - `--mirror` ensures all branches, tags, and refs are included.

   > E.g

   <img width="1806" height="1016" alt="image" src="https://github.com/user-attachments/assets/fd12c938-e958-43d7-9f9e-dcf538a4ae3f" />

2. Create a new repository on GitHub (empty).

      https://github.com/user-attachments/assets/ba8b1a16-4949-493c-bac2-4a63ba59b2f9

      > E.g:

      <img width="1906" height="993" alt="image" src="https://github.com/user-attachments/assets/b754113d-4a4b-4e45-a899-f4bbc622cb92" />

3. Push the mirrored repo to GitHub:
   ```bash
   cd repo.git
   git push --mirror https://github.com/username/repo.git
   ```

   > E.g:
   
   <img width="1908" height="997" alt="image" src="https://github.com/user-attachments/assets/de98ff11-e412-4e4c-959e-fb870f4aef97" />

   <img width="1912" height="991" alt="image" src="https://github.com/user-attachments/assets/6a35dce4-f6f3-4051-9da9-9d3861b8e55f" />

> At this point, your code and commit history are fully migrated.

   > E.g:

   <img width="1905" height="992" alt="image" src="https://github.com/user-attachments/assets/5a0b6e7b-1619-41a2-97c7-5db20c9fb431" />
   
   https://github.com/user-attachments/assets/21d82423-d51b-493c-b921-0e437c13e580

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
  <p>Refresh Date: 2026-01-25</p>
</div>
<!-- END BADGE -->
