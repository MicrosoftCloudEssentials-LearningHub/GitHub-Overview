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

</details>

<details>
<summary><b>Table of Content </b> (Click to expand)</summary>

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
        Epic
         └─ Feature
             └─ User Story
                 └─ Task

<img width="1908" height="991" alt="image" src="https://github.com/user-attachments/assets/2f04eb14-a2dc-41a4-a523-02b3075a5842" />

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

## Setup Azure Release Pipelines (CD)

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
