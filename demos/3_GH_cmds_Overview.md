# GitHub Commands - Overview 

Costa Rica

[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/) [brown9804](https://github.com/brown9804)

Last updated: 2026-01-20

----------------------

<details>
<summary><b>List of References </b> (Click to expand)</summary>

- [Repository limits](https://docs.github.com/en/repositories/creating-and-managing-repositories/repository-limits?utm_source=copilot.com)

</details>

## Check Repo Sizes in an Organization

1. Create a GitHub Personal Access Token (PAT): 
  - Go to `GitHub → Settings → Developer settings → Personal access tokens.`
  - Create a Fine‑grained token with at least read‑only repo scope.
  - If your org enforces SSO, click Authorize for your org after creating the token.
  - Copy the token (it looks like ghp_xxxxx...).

      <img width="1916" height="692" alt="image" src="https://github.com/user-attachments/assets/060baf25-03d4-428b-82b2-8335018e86bc" />

2. Store the Token in PowerShell:

    ~~~powershell
    $env:GITHUB_TOKEN="ghp_yourtokenhere"
    ~~~

3. Call the GitHub API: Run PowerShell script that lists all repos in your org with their sizes. Please change `{YOUR-ORG-NAME}`

      ~~~powershell
      $headers = @{ Authorization = "token $env:GITHUB_TOKEN" }
      $response = Invoke-WebRequest -Uri "https://api.github.com/orgs/MicrosoftCloudEssentials-LearningHub/repos?per_page=100" -Headers $headers
      $repos = $response.Content | ConvertFrom-Json
      
      # Show name and size in GB
      $repos | Select-Object name, @{Name="SizeGB";Expression={[math]::Round($_.size/(1024*1024),2)}} | Sort-Object SizeGB -Descending
      ~~~

      > E.g 

      <img width="1458" height="897" alt="image" src="https://github.com/user-attachments/assets/151e960b-f053-43ae-9946-d229df36756f" />


<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-1289-limegreen" alt="Total views">
  <p>Refresh Date: 2025-10-07</p>
</div>
<!-- END BADGE -->
