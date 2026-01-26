# Apps Dev + GitHub Pricing - Overview 

Costa Rica

[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/) [brown9804](https://github.com/brown9804)

Last updated: 2026-01-25

----------------------

> [!IMPORTANT]
> The information provided and any document (such as scripts, sample codes, etc.) is provided `AS-IS` and `WITH ALL FAULTS`.
> Pricing estimates are for `demonstration purposes only and do not reflect final pricing`. `Microsoft assumes no liability`
> for your use of this information and makes no guarantees or warranties, expressed or implied, regarding its accuracy or completeness,
> including any pricing details. `Please note that these demos are intended as a guide and are based on personal experiences. For official
> guidance, support, or more detailed information, please refer to Microsoft's official documentation or contact Microsoft directly`:
> [Microsoft Sales and Support](https://support.microsoft.com/contactus?ContactUsExperienceEntryPointAssetId=S.HP.SMC-HOME)

<details>
<summary><b>List of References </b> (Click to expand)</summary>
  
- [Visual Studio subscriptions pricing](https://visualstudio.microsoft.com/vs/pricing/?tab=paid-subscriptions)

</details>


> [!NOTE]
> - Visual Studio `Dev Platform`
> - Azure DevOps `Boards + Pipelines`
> - GitHub areas: `Code Platform`
>   - GitHub Enterprise Cloud `SaaS`
>   - GitHub Enterprise Server `Self‑Hosted`
>   - GitHub Copilot for Business `AI Productivity`
>   - GitHub Copilot for Enterprise `AI Productivity + Governance`
>   - GitHub Advanced Security (Code Scanning, Secret Scanning) `Security`
>   - GitHub Actions `CI/CD + Testing`
>   - GitHub Code Quality (coming soon) `Quality & Analysis`

## Visual Studio 

`Dev Platform`

> Free and Paid subscriptions: 

<img width="1907" height="1077" alt="image" src="https://github.com/user-attachments/assets/af6544af-713a-45c8-97df-6e48ac3df3e6" />

https://github.com/user-attachments/assets/b5eb82db-d047-4972-ab19-3692634dd0b8


## GitHub 

> - GitHub areas: `Code Platform`
>   - GitHub Enterprise Cloud `SaaS`
>   - GitHub Enterprise Server `Self‑Hosted`
>   - GitHub Copilot for Business `AI Productivity`
>   - GitHub Copilot for Enterprise `AI Productivity + Governance`
>   - GitHub Advanced Security (Code Scanning, Secret Scanning) `Security`
>   - GitHub Actions `CI/CD + Testing`
>   - GitHub Code Quality (coming soon) `Quality & Analysis`

### Hosting code

> [!TIP]
> - License cost per user → same
> - Total cost of ownership → different because Server requires your own infrastructure and operations 

| Feature Area            | GitHub Enterprise Cloud                         | GitHub Enterprise Server                         |
|-------------------------|--------------------------------------------------|---------------------------------------------------|
| Hosting Model           | Fully managed SaaS on GitHub’s infrastructure    | Self‑hosted on your own infrastructure or cloud   |
| Updates & Maintenance   | Automatic, continuous updates                    | Admin‑controlled upgrades and maintenance         |
| Scalability             | Elastic, handled by GitHub                       | Depends on customer hardware/resources            |
| Security Controls       | GitHub‑managed security + enterprise features    | Full control over security, networking, isolation |
| Compliance              | Meets GitHub’s cloud compliance certifications   | Customer responsible for compliance environment   |
| Access Requirements     | Internet access                                  | Private network, VPN, or internal access          |
| Customization           | Limited (cloud‑managed)                          | High (infrastructure, networking, integrations)   |
| Ideal For               | Organizations wanting zero‑maintenance SaaS      | Organizations needing full data residency control |


### Code Assistant:

> GitHub Copilot Personal vs. Businesses Use: 

| Section                                   | Details|
|-------------------------------------------|-----------------|
| **Free Version (Personal Use Only)**   | - GitHub Copilot Free is designed **only for individual developers**.<br>- It **cannot** be enabled on a managed organization account.<br>- When using the free version, **your code may be used to train GitHub’s AI models**. This is a key privacy consideration for anyone working with sensitive or proprietary code. |
| **Organization Use (Paid Plans)**      | - For companies or teams, GitHub offers **Copilot for Business** and **Copilot for Enterprise**.<br>- These plans are built for enterprise compliance and **do not use your code for training**.<br>- They include additional features like policy controls, audit logs, and enterprise-grade security.                                         |

> Pricing Details: 

> [!IMPORTANT]
> These are the prices as of today. Please make sure to check the current prices here in case anything has changed.
> - [Github Copilot](https://github.com/features/copilot/plans) - features and plans
> - [GitHub Enterprise pricing](https://azure.microsoft.com/en-us/pricing/details/githubenterprise/?msockid=38ec3806873362243e122ce086486339) - Table
> - [Visual Studio subscriptions pricing](https://visualstudio.microsoft.com/vs/pricing/?tab=paid-subscriptions) - plans
> - [Pricing calculator](https://azure.microsoft.com/en-us/pricing/calculator/?service=githubenterprise)

- **Copilot for Business**: \$19 per user/month.  
- **Copilot for Enterprise**: \$39 per user/month.  

    https://github.com/user-attachments/assets/a80d8ab6-e9d0-4ef6-9352-30098bbcbbb3

> [!TIP]
> - To use these, each user typically needs a **GitHub Enterprise license** (around \$20 per user/month). `When`: code to be available on GitHub; but, this is not a requirement. Click here to read more about `GHC standaone` [Quickstart for GitHub Copilot](https://docs.github.com/en/copilot/get-started/quickstart)
> - `Visual Studio subscribers can often add GitHub Enterprise for $0.12 per user/month, then add Copilot for $19.` Bundle with VS Studio license and GHE applies whether it's an Enterprise or Professional license, as today. More details here [Visual Studio subscriptions pricing](https://visualstudio.microsoft.com/vs/pricing/?tab=paid-subscriptions), [GitHub Enterprise pricing](https://azure.microsoft.com/en-us/pricing/details/githubenterprise/?msockid=38ec3806873362243e122ce086486339), [Github Copilot](https://github.com/features/copilot/plans) ` EA or SCE`
> - For large deals, GitHub sometimes offers a `1-month free trial`.

## DevSecOps 

> - Azure DevOps `Boards + Pipelines`
> - GitHub areas:
>   - GitHub Advanced Security (Code Scanning, Secret Scanning) `Security`
>   - GitHub Actions `CI/CD + Testing`
>   - GitHub Code Quality (coming soon) `Quality & Analysis`

| Area / Tool                                      | Category                | What It Does (Function)                                      | Value to DevSecOps (Why It Matters) |
|--------------------------------------------------|-------------------------|---------------------------------------|-------------------------------------------------------------------|
| **Azure DevOps: Boards + Pipelines**            | Planning + CI/CD        | - Boards: work tracking, backlog, planning.<br> - Pipelines: build, test, deploy automation. | - Creates traceability from idea → code → deployment. <br/> - Ensures repeatable builds, consistent releases, and governance across teams. |
| **GitHub Advanced Security**                     | Security                | Code scanning (SAST), secret scanning, dependency alerts.     | - Shifts security left by catching vulnerabilities *before* code reaches production. <br/> - Reduces risk, audit effort, and incident cost. |
| **GitHub Actions**                               | CI/CD + Testing         | Automates builds, tests, validations, and workflows directly in the repo. | - Ensures every commit is tested and validated. <br/> - Enables fast feedback loops and enforces quality gates at scale. |
| **GitHub Code Quality (coming soon)**            | Quality & Analysis      | Static analysis, maintainability checks, code health scoring. |-  Improves long‑term code maintainability. <br/> - Reduces technical debt and supports consistent engineering standards. |


<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-1289-limegreen" alt="Total views">
  <p>Refresh Date: 2026-01-25</p>
</div>
<!-- END BADGE -->
