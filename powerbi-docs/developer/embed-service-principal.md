---
title: Service principal with Power BI
description: Learn how to register an application within Azure Active Directory using service principal for use with embedding Power BI content.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: nishalit
ms.subservice: power-bi-developer
ms.topic: conceptual
ms.custom: ""
ms.date: 01/31/2018
---

# Service principal with Power BI (Preview)

With **service principal**, you can embed Power BI content into an application and use automation with Power BI using an **app-only** token. Service principal is beneficial when using **Power BI Embedded** or when **automating Power BI tasks and processes**.

When working with Power BI Embedded, there are advantages when using service principal.  A primary advantage is you do not need a master user account (Power BI Pro license) to authenticate into your application. Service principal uses an application ID and an application secret to authenticate the application.

As you automate various tasks with Power BI APIs, you can now script creating a service principal (app-only token) to use for authentication. You can script service principal to scale.

## Application and service principal relationship

To access resources that secure an Azure AD tenant, the entity that requires access represents a security principal. This action holds true for both users (user principal) and applications (service principal).

The security principal defines the access policy and permissions for users and applications in the Azure AD tenant. This access policy enables core features such as authentication of users and applications during sign in, and authorization during resource access. For more information, reference [service principal object](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object).

When you [register an Azure AD application](register-app.md) in the Azure portal, two objects are created in your Azure AD tenant:

* An application object
* A [service principal object]((https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object))

Consider the application object as the *global* representation of your application for use across all tenants, and the service principal as the *local* representation for use in a specific tenant.

The application object serves as the template from which common and default properties are *derived* for use in creating corresponding service principal objects.

A service principal is required per tenant where the application is used, enabling it to establish an identity for sign in and access to resources that are secured by the tenant. A single-tenant application has only one service principal (in its home tenant), created and consented for use during application registration.

## Service principal with Power BI Embedded

With service principal, you can mask your master user account information in your application by using an application ID (app ID) and an application secret (app secret). You don't have to hard-code a master user account into your application to authenticate.

Since **Power BI APIs** and **Power BI .NET SDK** now support calls using service principal, you can use all the [Power BI APIs](https://docs.microsoft.com/rest/api/power-bi/) with service principal. For example, you can make changes to workspaces such as create workspaces, add or remove users from workspaces, and import content into workspaces.

You can only use a service principal if your Power BI artifacts and resources are stored in a [Power BI new workspace](../service-create-the-new-workspaces.md).

## Service principal vs. master user account

There are differences between using a service principal token versus a standard master user account (Power BI Pro license) for authentication.

| Function | Master User Account | Service Principal |
|------------------------------------------------------|---------------------|-------------------|
| Sign in to the Power BI   service  | Yes | No |
| Works with app workspaces (v1) | Yes | No |
| Works with the new app   workspaces (v2) | Yes | Yes |
| Multi-factor authentication   (MFA) enabled in Azure | No | Yes |
| Use Power BI Rest APIs | Yes | Yes |
| Can be created via automation | No | Yes |
| Can install and edit   On-premises data gateway | Yes | No |
| Enabled in the Power BI Admin Portal | No | Yes |

## Get started with service principal

1. [Register an Azure AD application](register-app.md).

2. [Set up your Power BI environment](embed-sample-for-customers.md#set-up-your-power-bi-environment).

3. Now you can choose to embed your content either through the [sample application](https://app.powerbi.com/embedsetup/appownsdata) that you can download or within your own application.

    [Embed your content using the sample application](embed-sample-for-customers.md#embed-your-content-using-the-sample-application)

    [Embed your content within your application](embed-sample-for-customers.md#embed-your-content-within-your-application)

## Using Powershell to create service principal

1. Open Powershell as an administrator

2. Install the Azure AD module

    ```powershell
    Install-Module -Name AzureAD
    ```
3. Then run the command *Set-ExecutionPolicy -ExecutionPolicy Bypass*

    ```powershell
    Set-ExecutionPolicy -ExecutionPolicy Bypass
    ```
4. Run Powershell script

    ```powershell
    param (
    [string]$applicationName
    )

    # Login to Azure and be able to use the app cmdlets
    Connect-AzureAD
    Login-AzureRmAccount

    # Create a new AAD web application
    $App = New-AzureADApplication -DisplayName $applicationName -Homepage "https://localhost:44322" -ReplyUrls "https://localhost:44322"

    # Add service principal to the application (only for allowed users)
    New-AzureRmADServicePrincipal -ApplicationId $App.AppId
    ```

    > [!Note]
    > Once you exit out of the blade, it is not visible any more so save it. However, if you forget to save it, then you can just craete a new one.

## Migrate to service principal

You can take steps to migrate to use service principal if you're currently using a master user account authenticate into Power BI or your Power BI Embedded application.

1. First, you need to [Register an Azure AD application](register-app.md).

2. Then you need to create a [new workspace](../service-create-the-new-workspaces.md) in the Power BI service.

3. Then add or move Power BI artifacts into the new workspace.

4. Then with an admin master user account, sign in to Power BI and enable the service principal developer setting in the Power BI admin portal.

    ![Admin portal](media/embed-service-principal/admin-portal.png)

5. Then you need to add the service principal as an admin to the new workspace you created from step 2.

## Considerations and limitations

* Only works with the [new app workspaces](../service-create-the-new-workspaces.md).
* The **My Workspace** isn't supported.
* Dedicated capacity is required when moving to production.
* Need a master user account (Power BI Pro license) to log into Power BI to enable service principal in the admin portal.
* Can't install or manage on-premises data gateway.
* Can't sign into the Power BI portal.

## Next steps

* [Register an app](register-app.md)
* [Power BI Embedded for your customers](embed-sample-for-customers.md)
* [Application and service principal objects in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals)
