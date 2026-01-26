# GitHub - Overview

Costa Rica

[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/) [brown9804](https://github.com/brown9804)

Last updated: 2025-08-04

----------------------

- `GitHub → Repos (E2E source code, application, IaC, etc)` + `GHAS + GHC + etc`
- `ADO  →  Boards (Agile/Scrum methodologies) +  Pipelines (Testing, CI/CD)`

> GitHub is a web-based platform that provides hosting for software development and version control using Git. It offers a comprehensive suite of tools for collaboration, code management, and software delivery.

<div align="center">
  <img width="650" alt="image" src="https://github.com/user-attachments/assets/a3d413ce-b0d8-40a6-85d3-a3da825b34e3" style="border: 2px solid #4CAF50; border-radius: 5px; padding: 5px;"/>
</div>

> [!TIP]
> For current Azure DevOps users, Microsoft suggest `moving your repositories over to GitHub so you can make the most of the latest agentic AI features`. You can still `keep using Azure Boards, Pipelines, and other tools like Test Plans thanks to our integrations.` Also, `Azure DevOps basic usage rights now come with GitHub Enterprise`, and Microsoft `working on making the migration process and integrations between GitHub and Azure DevOps even smoother.`

<details>
<summary><b>List of References</b> (Click to expand)</summary>

- [GitHub Docs](https://docs.github.com): Comprehensive documentation for all GitHub features and workflows.
- [GitHub Actions](https://docs.github.com/en/actions): Learn how to automate workflows with GitHub Actions.
- [GitHub Pages](https://pages.github.com): Official guide to hosting static websites with GitHub Pages.
- [Git Reference](https://git-scm.com/docs): Official documentation for Git commands and workflows.
- [GitHub CLI](https://cli.github.com): Command-line interface for GitHub.
- [Pro Git Book](https://git-scm.com/book/en/v2): Free book on Git and version control.
- [GitHub Security Features](https://docs.github.com/en/code-security): Overview of GitHub's security tools.
- [Dependabot](https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically): Automate dependency updates.
- [CodeQL](https://codeql.github.com): Learn about GitHub's code scanning technology.
- [GitHub Discussions](https://github.com/github/feedback/discussions): Community forum for GitHub users.
- [GitHub Support](https://support.github.com): Contact GitHub support for help.

</details>

<details>
<summary><b>Table of content </b> (Click to expand)</summary>

- [Overview](#overview)
- [Development Workflow](#development-workflow)
- [Issues](#issues)
    - [Key Features](#key-features)
    - [Examples](#examples)
- [Projects](#projects)
    - [Key Features](#key-features)
    - [Examples](#examples)
- [GitHub Pages](#github-pages)
    - [Key Features](#key-features)
    - [Setup Process](#setup-process)
    - [Examples](#examples)
- [Security Tools](#security-tools)
    - [Key Features](#key-features)
    - [Examples](#examples)
- [Codespaces](#codespaces)
    - [Key Features](#key-features)
    - [Examples](#examples)
- [Areas](#areas)

</details>

## Overview 

| Concept | Definition |
|---------|------------|
| Git | A distributed version control system that tracks changes to files over time |
| Repository (Repo) | A project's folder containing all files and their revision history |
| Branch | A parallel version of the repository for isolated development work |
| Commit | A snapshot of changes with a unique ID and descriptive message |
| Pull Request (PR) | A proposal to merge changes from one branch into another |
| Merge | The process of integrating changes from one branch into another |

## Development Workflow

<details>
<summary><b>1. Create or Clone a Repository</b></summary>

- Initialize a new repository: `git init my-project`
- Clone an existing repository: `git clone https://github.com/username/repo.git`
- Public repos visible to everyone, private repos limited to collaborators
</details>

<details>
<summary><b>2. Branch Development</b></summary>

- Create and switch to a new branch: `git checkout -b feature-branch`
- List all branches: `git branch -a`
- Work in isolation without affecting the main codebase
</details>

<details>
<summary><b>3. Commit Changes</b></summary>

- Check status of changed files: `git status`
- Stage all changes: `git add .`
- Stage specific file: `git add <file name>`
- Commit staged changes: `git commit -m "<message>"`
- Build a detailed history of project modifications
</details>

<details>
<summary><b>4. Open Pull Request</b></summary>

- Push branch to remote repository: `git push origin <feature-branch name>`
- Use GitHub UI: Click `Compare & pull request`
- Describe changes, their purpose, and impact
</details>

<details>
<summary><b>5. Code Review and Discussion</b></summary>

- Review changes line by line in GitHub UI
- Add comments on specific lines
- Request changes or approve the pull request
- Ensure code quality and catch issues early
</details>

<details>
<summary><b>6. Automated Testing (CI)</b></summary>

- GitHub Actions run automated tests when PR is created
- Example workflow file (.github/workflows/ci.yml):
  ```yaml
  name: CI
  on: [push, pull_request]
  jobs:
    test:
      runs-on: ubuntu-latest
      steps:
        - uses: actions/checkout@v3
        - run: npm install
        - run: npm test
  ```
- Check test results in `Actions` tab on GitHub
</details>

<details>
<summary><b>7. Merge Approved Changes</b></summary>

- GitHub UI: Click `Merge pull request`
- Or command line:
  ```bash
  git checkout main
  git pull
  git merge feature-branch
  git push
  ```
- Features or fixes become part of the official project
</details>

<details>
<summary><b>8. Automated Deployment (CD)</b></summary>

- Deploy updated applications to production environments
- Example deployment workflow:
  ```yaml
  name: Deploy
  on:
    push:
      branches: [main]
  jobs:
    deploy:
      runs-on: ubuntu-latest
      steps:
        - uses: actions/checkout@v3
        - run: npm install
        - run: npm run deploy
  ```
- Release new versions to users automatically

</details>


## Issues

> Issues are GitHub's built-in tracking system for bugs, feature requests, and tasks. They provide a centralized location to discuss ideas, enhancements, and problems related to your project.

<details>
<summary><b>Expand for more details</b></summary>

### Key Features
- **Issue Templates**: Create standardized formats for bug reports, feature requests, etc.
- **Labels**: Categorize issues by type, priority, status (e.g., "bug", "enhancement", "high-priority")
- **Milestones**: Group issues into project phases or version releases
- **Assignees**: Delegate responsibility to specific team members
- **Mentions**: Tag team members using @username to request input
- **Task Lists**: Create checklists within issues using `- [ ]` syntax

### Examples

**Creating an issue via GitHub CLI:**
```bash
gh issue create --title "Login button doesn't work" --body "When clicking the login button, nothing happens."
```

**Example issue template:**
```yaml
name: Bug Report
description: File a bug report
body:
  - type: markdown
    attributes:
      value: |
        Thanks for taking the time to fill out this bug report!
  - type: input
    id: what-happened
    attributes:
      label: What happened?
      description: Also tell us, what did you expect to happen?
    validations:
      required: true
  - type: dropdown
    id: browsers
    attributes:
      label: What browsers are you seeing the problem on?
      multiple: true
      options:
        - Firefox
        - Chrome
        - Safari
        - Microsoft Edge
```

**Linking an issue to a pull request:**
```
This PR fixes #123 and addresses #456
```
</details>

## Projects

> Projects are flexible Kanban-style boards for organizing work and tracking progress across GitHub issues and pull requests.

<details>
<summary><b>Expand for more details</b></summary>

### Key Features
- **Boards**: Customizable Kanban-style boards with columns (e.g., To Do, In Progress, Done)
- **Cards**: Issues, pull requests, or notes that move between columns
- **Automation**: Automatically move cards based on events like PR creation
- **Views**: Table, board, or roadmap views for different perspectives
- **Custom Fields**: Add metadata like priority, effort, or custom categories
- **Filters**: Focus on specific aspects of the project by assignee, label, etc.

### Examples

**Basic project board structure:**
- To Do
- In Progress
- Review
- Done

**Automation rules example:**
- When issues are opened → Add to "To Do" column
- When pull requests are opened → Move card to "In Progress" column
- When pull requests are merged → Move card to "Done" column

**GitHub CLI commands:**
```bash
# Create a new project
gh project create "Q3 Feature Roadmap" --org "your-organization"

# Add an issue to a project
gh project item-add <project-number> --issue <issue-number>
```
</details>

## GitHub Pages

> GitHub Pages is a free hosting service for static websites directly from GitHub repositories, perfect for project documentation, blogs, portfolios, or simple web applications.

<details>
<summary><b>Expand for more details</b></summary>

### Key Features
- **Free Hosting**: No cost for public repositories
- **Custom Domains**: Connect your own domain name
- **HTTPS**: Automatic SSL certificate provisioning
- **Jekyll Integration**: Built-in support for Jekyll static site generator
- **Automatic Builds**: Sites rebuilt automatically when you push changes

### Setup Process
1. Create repository with content
2. Go to repository Settings → Pages
3. Select source branch/folder
4. (Optional) Configure custom domain
5. Site is published at username.github.io/repository

### Examples

**Simple index.html file:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>My GitHub Pages Site</title>
</head>
<body>
    <h1>Hello World!</h1>
    <p>This site is hosted with GitHub Pages.</p>
</body>
</html>
```

**Jekyll configuration (_config.yml):**
```yaml
theme: jekyll-theme-minimal
title: My Project Documentation
description: Comprehensive guides for using my awesome project
```

**Custom 404 page (404.html):**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Page Not Found</title>
</head>
<body>
    <h1>404 - Page Not Found</h1>
    <p>The page you were looking for doesn't exist.</p>
    <a href="/">Go back home</a>
</body>
</html>
```
</details>

## Security Tools

> GitHub provides a comprehensive suite of security tools to identify and fix vulnerabilities in your code and dependencies.

<details>
<summary><b>Expand for more details</b></summary>

### Key Features
- **Dependabot**: Automatically detects vulnerable dependencies and creates PRs to update them
- **Code Scanning**: Uses CodeQL to identify potential security issues in your code
- **Secret Scanning**: Prevents accidental credential exposure in your repositories
- **Security Advisories**: Private workspace for vulnerability reporting and fixes

### Examples

**Dependabot configuration (dependabot.yml):**
```yaml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "weekly"
    security-updates-only: true
```

**Code scanning workflow (.github/workflows/codeql.yml):**
```yaml
name: "CodeQL"
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
jobs:
  analyze:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: github/codeql-action/init@v2
      with:
        languages: javascript, python
    - uses: github/codeql-action/analyze@v2
```

**Security policy file (SECURITY.md):**
```markdown
# Security Policy

## Reporting a Vulnerability

Please report security vulnerabilities to security@example.com.

We will acknowledge receipt of your vulnerability report within 24 hours and send a more detailed response within 48 hours indicating next steps.
```
</details>

## Codespaces

> Codespaces provides cloud-based development environments that are fully configured and ready to code, eliminating environment setup time and `works on my machine` problems.

<details>
<summary><b>Expand for more details</b></summary>

### Key Features
- **Pre-configured Environments**: Start coding immediately without setup
- **Customization**: Define dev container configuration in repository
- **Extension Support**: Use VS Code extensions in the cloud
- **Port Forwarding**: Test web apps with public/private URL options
- **Persistent Storage**: Keep your work between sessions
- **Collaboration**: Share running environments with team members

### Examples

**Dev container configuration (.devcontainer/devcontainer.json):**
```json
{
  "name": "Node.js & MongoDB",
  "dockerComposeFile": "docker-compose.yml",
  "service": "app",
  "workspaceFolder": "/workspace",
  "extensions": [
    "dbaeumer.vscode-eslint",
    "mongodb.mongodb-vscode"
  ],
  "forwardPorts": [3000, 27017],
  "postCreateCommand": "npm install",
  "settings": {
    "terminal.integrated.defaultProfile.linux": "bash"
  }
}
```

**Docker Compose file (.devcontainer/docker-compose.yml):**
```yaml
version: '3'
services:
  app:
    build: 
      context: .
      dockerfile: Dockerfile
    volumes:
      - ..:/workspace:cached
    command: sleep infinity
    network_mode: service:db
  
  db:
    image: mongo:latest
    restart: unless-stopped
    volumes:
      - mongodb-data:/data/db

volumes:
  mongodb-data:
```

**GitHub CLI commands:**
```bash
# Create new codespace
gh codespace create

# Open an existing codespace in VS Code
gh codespace code

# Stop a codespace
gh codespace stop
```
</details>

## Areas

| **Feature/Area**                  | **Description**                                                                                     | **Purpose**                                                                                     |
|-----------------------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| **GitHub Enterprise Cloud**       | A cloud-hosted version of GitHub for businesses, offering advanced collaboration and security tools. | Provides scalability, security, and compliance for organizations using GitHub in the cloud.    |
| **GitHub Enterprise Server**      | A self-hosted version of GitHub for businesses, deployed on-premises or in a private cloud.         | Offers full control over GitHub infrastructure for organizations with strict compliance needs. |
| **GitHub Advanced Security**      | Includes tools like Code Scanning and Secret Scanning to identify vulnerabilities in code.          | Helps secure codebases by detecting vulnerabilities and exposed secrets.                       |
| **GitHub Copilot for Business**   | AI-powered code completion tool tailored for teams and organizations.                              | Boosts developer productivity by suggesting code snippets and automating repetitive tasks.     |
| **GitHub Copilot for Enterprise** | AI-powered code completion tool designed for large-scale enterprise use.                           | Provides AI-driven coding assistance with enterprise-grade security and scalability.           |
| **GitHub Actions**                | Automation platform for CI/CD workflows, enabling testing, building, and deployment.               | Streamlines development workflows by automating repetitive tasks.|
| **GitHub Code Quality**           | A forthcoming feature focused on improving code quality through automated analysis.                | Aims to provide insights and recommendations to improve code maintainability and readability.  |

<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-1289-limegreen" alt="Total views">
  <p>Refresh Date: 2025-10-07</p>
</div>
<!-- END BADGE -->

