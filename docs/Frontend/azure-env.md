---
title: Azure Setup
---

# Setup Prerequisites
* Microsoft Entra Tenant
* Microsoft Entra Subscription

# Install Azure PowerShell Module
```PowerShell
Install-Module -Name Az -Repository PSGallery -Force
```

# Create Resource Group
```PowerShell
Connect-AzAccount
```

```Powershell
New-AzResourceGroup -Name rg-SmashGrade -Location switzerlandNorth
```

# Create a Static Web App (Later we will be able to deploy a template)
Navigate to: **Resource groups > rg-SmashGrade > + Create**
![image](https://github.com/SmashGrade/SmashGrade-App/assets/54718339/168a6c9b-85f2-4e01-86a1-f248b1867356)

1. Select your Subscription
2. Your created Resource Group
3. define a name (starting with stapp-* according to the best practices https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations)
4. select Azure Staging Region
5. Sign in to GitHub an request access token for SmashGrade GitHub Repo
6. Select the Organization, Repo and Branch
7. Build Presents -> React
8. App location `/`
9. Api location: (default)
10. Output location: 'dist'

![image](https://github.com/SmashGrade/SmashGrade-App/assets/54718339/92c19773-755d-464f-863b-8f9c2c18badd)

# Short Overview

## Overview Page
On the Overview section you have all the important stuff like the URL for the web page itself or the GitHub Action URL.
![image](https://github.com/SmashGrade/SmashGrade-App/assets/54718339/1f8ffc68-02d5-498e-bd61-8d15bcab86f7)

## Define a password
This will result in a password prompt each time you open the page
![image](https://github.com/SmashGrade/SmashGrade-App/assets/54718339/deca35f3-15ea-4858-8f54-77381259ba04)


## Artifacts created by Azure in GitHub

GitHub Action
![image](https://github.com/SmashGrade/SmashGrade-App/assets/54718339/fe0aa9c6-9abf-4bfa-ade0-aed4b7414c9b)

Secrets for GitHub Actions
![image](https://github.com/SmashGrade/SmashGrade-App/assets/54718339/0d6cd5ed-9795-46ae-8662-c636c575e784)

Workflow File:
![image](https://github.com/SmashGrade/SmashGrade-App/assets/54718339/17be9ed6-b374-4185-981d-81f113c90e94)

<hr>

# Create Web App
Create a new Web App:
![image](https://github.com/SmashGrade/SmashGrade-App/assets/54718339/0722551d-eec5-4500-a743-7292ec10d576)

Set Deployment settings:
![image](https://github.com/SmashGrade/SmashGrade-App/assets/54718339/95a644bf-3660-4df2-bcb0-4f9d461b6415)

Review + create

Create the Git Actions as defined in the following Branch:
https://github.com/SmashGrade/SmashGrade-App/tree/%2332-deploy-pr-to-azure-slot

