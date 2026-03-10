# Minimum Access Requirements <br/> for CI/CD Pipelines - Overview

Costa Rica

[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/) [brown9804](https://github.com/brown9804)

Last updated: 2026-01-25

----------------------

> One of best practices is `starting with the built-in Contributor role as a template`,
> then `subtract what isn’t needed and add what Contributor misses.`
> Microsoft provides tools to fetch a role definition. For example, [you can get the JSON for Contributor and modify it](https://learn.microsoft.com/en-us/azure/role-based-access-control/custom-roles).
> In practice, you might create two roles for pipelines: one `“Deployment Contributor”` that has all [resource actions](https://learn.microsoft.com/en-us/azure/role-based-access-control/resource-provider-operations) `(like
> Contributor minus RBAC),` and another `“Access Manager”` role with `just Microsoft.Authorization/roleAssignments/*`


<details>
<summary><b>List of References </b> (Click to expand)</summary>

- [Azure roles, Microsoft Entra roles, and classic subscription administrator roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/rbac-and-directory-admin-roles)

    <img width="810" height="542" alt="image" src="https://github.com/user-attachments/assets/0971055e-1f16-4fee-b826-3466cc67b027" />

- [Azure permissions](https://learn.microsoft.com/en-us/azure/role-based-access-control/resource-provider-operations)
- [Azure custom roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/custom-roles)
- [Tutorial: Create an Azure custom role using Azure CLI](https://learn.microsoft.com/en-us/azure/role-based-access-control/tutorial-custom-role-cli)
- [About pipeline security roles](https://learn.microsoft.com/en-us/azure/devops/organizations/security/about-security-roles?view=azure-devops)
- [Manage security in Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/policies/permissions?view=azure-devops)
- [Secure your Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/security/overview?toc=%2Fazure%2Fdevops%2Forganizations%2Fsecurity%2Ftoc.json&view=azure-devops)

</details>

```mermaid
graph TD
    A[Dev Platform - VS/VSC] --> B[Code Platform - GHE/GHES]
    B --> C[AI Productivity - GHC]
    B --> D[Security, Code Scanning, Secret Scanning - GHAS]
    B --> E[Quality & Analysis - GHCQ]
    A --> F[Boards + Pipelines - ADO]
    F --> G[CI/CD + Testing - GHA]
```

> For example: How linking from Resource Manager and CI/CD to Microsoft Entra ID is the key to having an end-to-end governance model.

<img width="400" height="234" alt="image" src="https://github.com/user-attachments/assets/908ea445-83e5-489e-8840-0083ae70524d" />

<img width="850" height="194" alt="image" src="https://github.com/user-attachments/assets/214a26b9-0213-41e5-b0f2-b001d550a131" />

> [!NOTE]
> Azure DevOps repos / GitHub repos:

<img width="850" height="626" alt="image" src="https://github.com/user-attachments/assets/b84dbbf1-0b76-4d03-886b-7df5bd55b482" />

From [End-to-end governance in Azure when using CI/CD](https://learn.microsoft.com/en-us/devops/operate/governance-cicd)

<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-1289-limegreen" alt="Total views">
  <p>Refresh Date: 2026-01-25</p>
</div>
<!-- END BADGE -->
