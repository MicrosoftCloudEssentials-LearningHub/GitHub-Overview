# Demo: DevSecOps - Overview 

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

- [Connect Azure DevOps environments to Defender for Cloud](https://learn.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-devops)
- [Configure the Microsoft Security DevOps Azure DevOps extension](https://learn.microsoft.com/en-us/azure/defender-for-cloud/configure-azure-devops-extension)
- [Configure GitHub Advanced Security for Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/repos/security/configure-github-advanced-security-features?view=azure-devops&tabs=yaml&pivots=standalone-ghazdo#set-up-dependency-scanning)
- [Deploy Defender for Containers on Azure (AKS) programmatically](https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-containers-azure-enable-programmatically?tabs=aks-cli)
- [ARM template documentation](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/)
- [Visual Studio subscriptions pricing](https://visualstudio.microsoft.com/vs/pricing/?tab=paid-subscriptions)
- [GitHub Enterprise Pricing](https://github.com/pricing)
- [GitHub Advanced Security license billing](https://docs.github.com/en/billing/concepts/product-billing/github-advanced-security)
- [GitHub Actions billing](https://docs.github.com/en/billing/concepts/product-billing/github-actions)
- [GitHub Code Quality billing](https://docs.github.com/en/billing/concepts/product-billing/github-code-quality)
- [Pricing for Azure DevOps](https://azure.microsoft.com/en-us/pricing/details/devops/azure-devops-services/?msockid=38ec3806873362243e122ce086486339)
- [GitHub pricing options](https://azure.microsoft.com/en-us/pricing/details/githubenterprise/?msockid=38ec3806873362243e122ce086486339)
- [Microsoft Use Case Explorer](https://aiusecaseexplorer.microsoft.com/)
- [Configure GitHub Advanced Security for Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/repos/security/configure-github-advanced-security-features?view=azure-devops&tabs=yaml&pivots=standalone-ghazdo#set-up-dependency-scanning)
- [Overview of role-based access control in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/custom-overview)
- [Configure a GitHub Enterprise Cloud Organization for Single sign-on with Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/saas-apps/github-tutorial)
- [Authenticate to Azure DevOps with Microsoft Entra ID](https://learn.microsoft.com/en-us/azure/devops/integrate/get-started/authentication/entra?view=azure-devops)
- [What is managed identities for Azure resources?](https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview)
- [Zero Trust security in Azure](https://learn.microsoft.com/en-us/azure/security/fundamentals/zero-trust)

    <img width="650" alt="image" src="https://github.com/user-attachments/assets/e5f3ab8b-e14c-46c4-b4d0-c43581684371" />

</details>

<details>
<summary><b>Table of Content </b> (Click to expand)</summary>

- [DevOps + Security](#devops--security)
- [Setup Azure DevOps](#setup-azure-devops)
  - [Azure DevOps: Boards + Pipelines - pricing example](#azure-devops-boards--pipelines----pricing-example)
- [GHE + VS + GHC setup](#ghe--vs--ghc-setup)
- [Setup GitHub Actions + GHAS + GHCQ (CI)](#setup-github-actions--ghas--ghcq-ci)
  - [GitHub Advanced Security - pricing example](#github-advanced-security---pricing-example)
  - [GitHub Actions - pricing example](#github-actions---pricing-example)
  - [GitHub Code Quality - pricing example](#github-code-quality---pricing-example)
  - [Turn on core GHAS features (org → repo baseline)](#turn-on-core-ghas-features-org--repo-baseline)
  - [Enable CodeQL code scanning (CI integrated)](#enable-codeql-code-scanning-ci-integrated)
- [Setup Azure Release Pipelines (CD)](#setup-azure-release-pipelines-cd)
- [Monitoring + Observability (Telemetry)](#monitoring--observability-telemetry)
  
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

## DevOps + Security

> Demo about DevSecOps, we start by setting up a new `project in Azure DevOps` and using Boards to plan work with epics, features, and user stories.
> Then link a fresh `GitHub Enterprise repo to track the progress of development`, `coding in Visual Studio with GitHub Copilot to accelerate productivity and enforce governance`.
> From there, configure `Azure DevOps Pipelines to provision and deploy the Azure infrastructure consistently`, while using `GitHub Actions for application builds, integration testing,
> and regression checks to ensure nothing breaks.` Layer in `GitHub Advanced Security for code scanning, secret detection, and dependency alerts, and add GitHub Code Quality for maintainability analysis.`
>  Finally, `deploy through Azure DevOps Release Pipelines,` and `monitor with Azure Monitor and Application Insights to close the loop with observability and continuous feedback.`
>  This flow demonstrates how planning, coding, building, testing, securing, deploying, and monitoring all integrate seamlessly in a DevSecOps pipeline.

<div align="center">
  <img width="550" alt="image" src="https://github.com/user-attachments/assets/8caa4fb9-e78c-4df6-a366-675ae50a3a8f" style="border: 2px solid #4CAF50; border-radius: 5px; padding: 5px;"/>
</div>

| **SDLC Stage** | **Area / Tool** | **What It Does (Function)** | **Value to DevSecOps (Why It Matters)** |
|----------------|-----------------|-----------------------------|-----------------------------------------|
| **Plan**       | Azure DevOps Boards | - Work tracking <br/> - Backlog management <br/> - Sprint planning | - Creates traceability from idea → code → deployment <br/> - Aligns teams with agile processes |
| **Code**       | Visual Studio / VS Code <br/> GitHub Copilot (Business/Enterprise) | - IDE integration, debugging, extensions <br/> - AI-assisted coding <br/> - Governance features (Enterprise) | - Boosts developer speed and productivity <br/> - Ensures AI suggestions comply with organizational policies |
| **Build**      | Azure DevOps Pipelines <br/> GitHub Actions | - YAML pipelines, multi-stage builds <br/> - Workflow automation, CI/CD | - Ensures repeatable builds and consistent releases <br/> - Provides fast feedback loops |
| **Test**       | Azure DevOps Test Plans <br/> GitHub Actions | - Manual + automated test management <br/> - Traceability from requirements → tests → deployments <br/> - Automated validations in workflows | - Strengthens quality assurance <br/> - Provides visibility and accountability across lifecycle |
| **Secure**     | GitHub Advanced Security <br/> Azure Security Center + Defender for Cloud | - Code scanning (SAST) <br/> - Secret scanning <br/> - Dependency alerts <br/> - Runtime monitoring <br/> - Compliance dashboards | - Shifts security left by catching vulnerabilities early <br/> - Protects workloads post-deployment <br/> - Ensures compliance with CIS, NIST, ISO standards |
| **Deploy**     | Azure DevOps Release Pipelines <br/> GitHub Actions | - Canary, blue-green deployments <br/> - Controlled release management <br/> - Direct deploy to Azure services | - Provides enterprise-grade deployment strategies <br/> - Enables reliable and governed releases |
| **Monitor**    | Azure Monitor + Application Insights | - Collects logs, metrics, traces <br/> - Provides alerts and dashboards | - Enables observability and feedback loops <br/> - Feeds insights back into Boards for continuous improvement |
| **Quality & Governance (cross-cutting)** | GitHub Code Quality (coming soon) <br/> GitHub Copilot for Enterprise | - Static analysis <br/> - Maintainability checks <br/> - Governance features for AI suggestions | - Improves long-term code maintainability <br/> - Reduces technical debt <br/> - Ensures AI adoption aligns with organizational standards |

## Setup Azure DevOps 

1. Use one of you existing organizations or create a new one: [Azure DevOps](https://aex.dev.azure.com/)

  <img width="650" alt="image" src="https://github.com/user-attachments/assets/90846104-ced9-466f-935f-f833e155bc69" />

  <img width="650" alt="image" src="https://github.com/user-attachments/assets/e10379c8-b8fe-4e98-afa9-ac24ff6005f6" />

  <img width="650"  alt="image" src="https://github.com/user-attachments/assets/cbe06958-f783-4a90-9e7b-d10935c8ebb7" />

2. Create a project: 

  <img width="650" alt="image" src="https://github.com/user-attachments/assets/195ddaab-60be-4c8c-b792-47a961d8a2c6" />

  <img width="1882" height="988" alt="image" src="https://github.com/user-attachments/assets/c493e8fb-9724-45a9-9272-ac8828be4346" />

> Depending on the project type you will see more type of work itmes, for example Agile:

<img width="1905" height="992" alt="image" src="https://github.com/user-attachments/assets/b8ce0294-1204-4adb-afcc-eb711c31b0c7" />

> For example:

  <img width="650" alt="image" src="https://github.com/user-attachments/assets/62f4d01a-8ccb-42c5-b1fe-dfe5384df5f0" />
  
  <img width="650" alt="image" src="https://github.com/user-attachments/assets/592e17aa-d09f-420d-a2f0-c945bd6c05d3" />

> [!NOTE]
> Your project now exists but is empty.

3. Plan your project. Example of plan: [Demo_DevSecOps_E2E_Backlog_example](./docs/Demo_DevSecOps_E2E_Backlog_example.xlsx)

> [!NOTE]
> Azure DevOps supports Excel integration via the Azure DevOps Office Integration add‑in.
> - You can export work items (epics, features, user stories) to Excel.
> - You can bulk edit or create work items in Excel (e.g., fill in rows for epics/features/stories).
> - Then you can publish back to Azure DevOps Boards directly from Excel.

> For example, let's image you have:
> - Azure DevOps project already exists
> - You have Basic access or higher
> - Excel desktop app installed
> - Your .xlsx contains work items (Epics, Features, Stories, Tasks)

> [!IMPORTANT]
> - You must still publish in order:
> - Epics
> - Features
> - User Stories
> - Tasks

> Epics, for example:

https://github.com/user-attachments/assets/c6a9acf3-b244-4d19-99d8-2f17a92ade45

<img width="1905" height="993" alt="image" src="https://github.com/user-attachments/assets/9787afa4-acc1-4a8f-8453-782044f0a8be" />

<img width="1899" height="990" alt="image" src="https://github.com/user-attachments/assets/a29fbc40-dbfc-43ac-a6c3-cd6cf9114a67" />

> [!NOTE]
> How to add more layers for project management:

https://github.com/user-attachments/assets/3564ddb6-a76c-4003-8f72-f328d0a21f97

> Use this **only for flat imports** (stories only).

1.  Go to **Boards → Work Items**
2.  Click **Import Work Items**

    <img width="1908" height="990" alt="image" src="https://github.com/user-attachments/assets/04869184-dff0-4b6c-8c54-3b60be451290" />

3.  Upload CSV
4.  Map fields manually

> Validate in Azure DevOps. In the web portal:

-  Go to **Boards → Backlogs**
-  Toggle **Epics / Features / Stories**
-  Confirm hierarchy:
```
        Epic
         └─ Feature
             └─ User Story
                 └─ Task
```
<img width="1908" height="991" alt="image" src="https://github.com/user-attachments/assets/2f04eb14-a2dc-41a4-a523-02b3075a5842" />

<details>
<summary><b> Azure DevOps: Boards + Pipelines  - pricing example </b> (Click to expand)</summary>

> Click here to read more about:
- [Pricing for Azure DevOps](https://azure.microsoft.com/en-us/pricing/details/devops/azure-devops-services/?msockid=38ec3806873362243e122ce086486339)
- [GitHub pricing options](https://azure.microsoft.com/en-us/pricing/details/githubenterprise/?msockid=38ec3806873362243e122ce086486339)

<img width="956" height="982" alt="image" src="https://github.com/user-attachments/assets/4e60d31c-935b-4c81-a1ad-f4d5fa6c65df" />

https://github.com/user-attachments/assets/b8f0d004-32b4-4480-84b1-e80601be2863

</details>

## GHE + VS + GHC setup 

> This process enables secure, enterprise-managed deployment of GitHub Copilot

1. Create a GitHub account for your organization. 
2. Please go here [Start your premium free trial by choosing an enterprise type](https://github.com/account/enterprises/new?ref_cta=GHEC+trial&ref_loc=setting+up+a+trial+of+github+enterprise+cloud&ref_page=docs), and start a GitHub Enterprise trial (includes Copilot and advanced security). 
3. Select the `Enterprise Managed Users` option.

   <img width="1907" height="855" alt="image" src="https://github.com/user-attachments/assets/e9a37cd5-7357-4de9-a46e-9ebc43f06e4e" />

4. Enter required organization details and a short code for user management.

   <img width="735" height="855" alt="image" src="https://github.com/user-attachments/assets/49224974-a585-4db4-bf1f-ef43ab4a00c2" />

6. Set up Single Sign-On (SSO) with your identity provider. Click here to read the steps: [GitHub Enterprise Cloud Enterprise Managed Users - Microsoft Entra ID / Azure AD Single Sign-On (SSO) Integration Guide](https://se-resource-library.octodemo.com/Azure_SSO_EMU)
7. Link your Azure subscription for billing (optional during trial). Click here to read the steps: [How to link Azure subscription to your GitHub's enterprise account](https://se-resource-library.octodemo.com/Link_Azure_Subscription)
8. Add users to the enterprise and assign Copilot seats. Click here to read how: [GitHub Copilot Business - Setup Guide](https://se-resource-library.octodemo.com/GitHub_Copilot_Business)
9. Users install the Copilot extension in their IDE.

    <img width="1922" height="1011" alt="image" src="https://github.com/user-attachments/assets/ad383755-2e02-471c-9633-d8a974f062c8" />

10. Users activate their accounts and Copilot access is enabled automatically.

    <img width="1917" height="1013" alt="image" src="https://github.com/user-attachments/assets/8fffd583-954f-4308-9b62-3eba70f44529" />

## Setup GitHub Actions + GHAS + GHCQ (CI)

> Continuous Integration (CI) is a software development practice where
> developers frequently integrate their code changes into a shared repository,
> allowing for automated builds and tests to ensure code quality and functionality.

<details>
<summary><b>GitHub Advanced Security - pricing example </b> (Click to expand)</summary>

> Click here to read more about:
- [GitHub Enterprise Pricing](https://github.com/pricing)
- [GitHub Advanced Security license billing](https://docs.github.com/en/billing/concepts/product-billing/github-advanced-security)
- [GitHub pricing options](https://azure.microsoft.com/en-us/pricing/details/githubenterprise/?msockid=38ec3806873362243e122ce086486339)


<img width="1907" height="991" alt="image" src="https://github.com/user-attachments/assets/9d21b569-1a7a-448c-955d-949e79a85a45" />

> E.g:

<img width="1189" height="596" alt="image" src="https://github.com/user-attachments/assets/13d9fba1-3322-47a8-94e7-9d907342adac" />

</details>

<details>
<summary><b> GitHub Actions - pricing example </b> (Click to expand)</summary>

> Click here to read more about:
- [GitHub Enterprise Pricing](https://github.com/pricing)
- [GitHub Actions billing](https://docs.github.com/en/billing/concepts/product-billing/github-actions)
- [GitHub pricing options](https://azure.microsoft.com/en-us/pricing/details/githubenterprise/?msockid=38ec3806873362243e122ce086486339)

<img width="1115" height="958" alt="image" src="https://github.com/user-attachments/assets/47722cf9-a093-4c1f-8894-8aab57f74adf" />

https://github.com/user-attachments/assets/eb1b1c94-48f5-4136-9818-e4c356317b3b

</details>


<details>
<summary><b> GitHub Code Quality - pricing example </b> (Click to expand)</summary>

> Click here to read more about:
- [GitHub Enterprise Pricing](https://github.com/pricing)
- [GitHub Code Quality billing](https://docs.github.com/en/billing/concepts/product-billing/github-code-quality)
- [GitHub pricing options](https://azure.microsoft.com/en-us/pricing/details/githubenterprise/?msockid=38ec3806873362243e122ce086486339)

https://github.com/user-attachments/assets/de20f063-d70a-42d0-bb64-dd6acef85c59

</details>


1. Link the existing, or create new GitHub repository with Azure DevOps:

     <img width="650" alt="image" src="https://github.com/user-attachments/assets/6ecd79ce-b6cb-40ec-b897-b2dba10572a0" />

     > For example: `With new repo`

      https://github.com/user-attachments/assets/e693afe4-72b9-4cbd-ab88-b897debc6395

      <img width="1924" height="1076" alt="image" src="https://github.com/user-attachments/assets/b5344622-552a-4629-ba9b-b18a4de2e129" />

     > Example with existing GH repo:

     https://github.com/user-attachments/assets/82238805-a84d-4ec9-8d1f-f78d285fab31

2. Relate work items with either existing history or new work:

      https://github.com/user-attachments/assets/dfcea8b1-7a76-447f-8e34-97658ac35426

### Turn on core GHAS features (org → repo baseline)

> Why: Code scanning (CodeQL) finds code vulnerabilities; secret scanning prevents credential leaks (pushes can be blocked with Push protection); dependency features surface known CVEs and auto‑PR fixes (Dependabot).


| **Scope**        | **Features to Enable**                                                                 | **Where to Enable**                                                                 | **Value to DevSecOps**                                                                 |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| **Organization** | - Code Scanning <br/> - Secret Scanning + Push Protection <br/> - Dependency Graph + Dependabot Alerts <br/> - Security Configurations | Org → Settings → Code security and analysis <br/> Org → Settings → Security configurations | - Ensures consistent security baseline across all repos <br/> - Shifts security left <br/> - Provides supply chain visibility <br/> - Reduces manual setup effort |
| **Repository**   | - Code Scanning (CodeQL) <br/> - Secret Scanning + Push Protection <br/> - Dependency Graph + Dependabot Alerts | Repo → Settings → Code security and analysis | - Provides repo‑specific vulnerability detection <br/> - Protects sensitive data <br/> - Ensures supply chain security at repo level |

`Features include Code Scanning (CodeQL), Secret Scanning + Push Protection, and Dependency Graph/Dependabot alerts.`

> Org‑level enablement is recommended for consistency and scale.

<img width="1914" height="1086" alt="image" src="https://github.com/user-attachments/assets/beaf0d22-6a76-4d1a-aa2d-afaf56327cb1" />

> Repo‑level enablement is useful when org defaults aren’t applied or for exceptions.

<img width="1910" height="995" alt="image" src="https://github.com/user-attachments/assets/20e86d4f-7c50-441b-abf6-b28432d9739d" />

https://github.com/user-attachments/assets/fe505254-f1b9-4144-9a4b-4553f9fbe521

### Enable CodeQL code scanning (CI integrated)

https://github.com/user-attachments/assets/458d8f3b-6fa0-40c8-a87e-60cef45c442a

<img width="650" alt="image" src="https://github.com/user-attachments/assets/a90ebc61-82f6-4f2a-97ca-872ec940e857" />

> [!TIP]
> Developer pushes code → CI runs → security & quality checks happen automatically:
> - GitHub Actions runs build + tests
> - CodeQL analyzes the code (and workflows)
> - Secret scanning checks for leaked credentials
> - Dependency review checks new libraries
> - Results appear in Security tab
> - Branch protection can block the merge if issues are found

https://github.com/user-attachments/assets/c2edf4ff-3bd6-487d-86a1-060d67364f7c

<img width="1535" height="936" alt="image" src="https://github.com/user-attachments/assets/cc803cdb-6d3f-41ca-9aae-c1b55456081a" />

## Setup Azure Release Pipelines (CD)

> Click here to read more about [Create your first pipeline](https://learn.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=python%2Cbrowser). For example, this is how it looks:

https://github.com/user-attachments/assets/773adf4c-9ab4-429e-9c13-f6f8a06a4c2b

## Monitoring + Observability (Telemetry)

> - `Observability `is particularly useful for diagnosing problems and `understanding the root cause of issues.`
> - `Monitoring` helps ensure a system is `working correctly and allows proactive problem detection and resolution before they become critical`. We can say, therefore, monitoring is a subset of telemetry. It provides deeper monitoring capabilities and a comprehensive understanding of the system.
> - `Telemetry` is used to collect and transmit data from remote sources, especially in hard-to-reach or hazardous environments. It is commonly used `for performance monitoring, asset tracking, and predictive maintenance.`

<div align="center">
  <img width="550" alt="image" src="https://github.com/user-attachments/assets/876e8acd-7974-4054-bbe9-a00cef88beaf" style="border: 2px solid #4CAF50; border-radius: 5px; padding: 5px;"/>
</div>

> Click here to read more about [Centralized Logging Framework - Overview](https://github.com/brown9804/Centralized-Logging-Framework)

<img width="650" alt="image" src="https://github.com/user-attachments/assets/d6a67c5b-c237-407b-b674-23ac034a019a" />


<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-1289-limegreen" alt="Total views">
  <p>Refresh Date: 2026-01-25</p>
</div>
<!-- END BADGE -->
