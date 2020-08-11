---
title: Considerations for generating an embedded token
description: Learn about the considerations and limitations when generating an embedded token
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ""
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.custom: ""
ms.date: 07/20/2020
---

# Consideration for generating an embedded token

[Generate token](https://docs.microsoft.com/rest/api/power-bi/embedtoken) is a REST API that lets you generate a token for embedding a Power BI item in an app or a website. The token is used to authenticate...

The following Power BI items:

* Dashboards

* Datasets

* Reports

* Tiles

## Workspace versions

Power BI has two workspace versions, a *classic* workspace, and a *new* workspace. You can learn more about the differences between these workspaces in [new and classic workspace differences](../../collaborate-share/service-new-workspaces#new-and-classic-workspace-differences.md).

When creating an embed token, different workspaces have different considerations and limitations.

|                  |*Classic* workspace |*New* workspace|
|------------------|---------|--------|
|**Considerations**|Dataset and item must be in the same workspace  |Dataset and item can be in two different *new* workspaces |
|**Workspace permissions**|The user or service principal must be at least a member of the workspace the item is in  |The user or service principal must be an admin of the workspace |
|**Write and reshare permissions**|The user or service principal must be at least a member of the workspace, or a contributor in the workspace the item is in   |Not required |

>[!NOTE]
>You cannot create an embed token for [My workspace](../../consumer/end-user-workspaces#types-of-workspaces.md).

## Row Level Security

When generating a token for embedding a [Row Level Security (RLS)](embedded-row-level-security.md) report, you can choose to use a different identity than the identity of the service principal or user you're generating the token with. Using this option, you can display embedded information according to the user you're targeting. For example, in your application you can ask users to sign in, and then display a report that only contains sales information if the signed in user is a sales employee.  

### Service principal

|RLS service  |Service principal  |Identity override  |
|---------|---------|---------|
|Cloud RLS     |         |         |
|RDL     |         |         |
|AS on prem     |         |         |
|AS Azure     |         |         |
|Single Sign On (SSO)     |         |         |
|SSO and cloud RLS     |         |         |


### Master user

With a master user you cannot


## Next steps

>[!div class="nextstepaction"]
>[Register an app](register-app.md)

> [!div class="nextstepaction"]
>[Power BI Embedded for your customers](embed-sample-for-customers.md)

>[!div class="nextstepaction"]
>[Application and service principal objects in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals)

>[!div class="nextstepaction"]
>[Row-level security using on-premises data gateway with service principal](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal)

>[!div class="nextstepaction"]
>[Embed Power BI content with service principal and a certificate](embed-service-principal-certificate.md)
