---
title: Distribute Power BI content to external guest users with Azure AD B2B
description: Power BI integrates with Azure Active Directory Business-to-business (Azure AD B2B) to allow secure distribution of Power BI content to guest users outside the organization.
services: powerbi
documentationcenter: ''
author: guyinacube
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''

ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: asaxton
---
# Distribute Power BI content to external guest users with Azure AD B2B

Power BI integrates with Azure Active Directory Business-to-business (Azure AD B2B) to allow secure distribution of Power BI content to guest users outside the organization, while still maintaining control over the internal data.

> [!VIDEO https://www.youtube.com/embed/xxQWEQ1NnlY]

> [!NOTE]
> This feature is not currently available with the Power BI mobile apps. On a mobile device, you can view Power BI content shared using Azure AD B2B in a browser. 
> 
> 


## Invite guest users

There are two ways to invite guest users to your Power BI tenant: planned invites or ad-hoc invites. Invitations are only needed the first time an external user is invited to your organization.

### Planned invites

A planned invite is performed within the Microsoft Azure Portal in Azure AD or using PowerShell. This is the option to use if you know which users must be invited. 

**Creating the guest users in the Azure AD portal requires that you be a tenant admin.**

1. Navigate to the [Azure Portal](https://portal.azure.com) and select **Azure Active Directory**.

2. Navigate to **Users and groups** > **All users** > **New guest user**.

    ![Azure AD Portal - New Guest User](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

3. Enter the **email address** and **personal message**.

    ![Azure AD Portal - new guest user invite message](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

4. Select **Invite**.

To invite more than one guest user, use PowerShell. For more information, see [Azure Active Directory B2B collaboration code and PowerShell samples](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-code-samples).

The guest user needs to select **Get Started** in the email invitation they receive. The guest user is then added to the tenant.

![Guest user email invitation](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### Ad-hoc invites

To perform an invite at anytime, add the external user to the access list of an app when publishing it.

![External user added to App access list](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

The guest user will receive an email indicating the app has been shared with them.

![Email for app shared with guest user](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

The guest user must sign in with their organization email address. They will be prompted to accept the invitation after signing in. After sign in, the guest user is redirected to the app content. To return to the app, bookmark the link, or save the email.

## Licensing

The guest user will need to have the proper licensing in place to view the app that was shared. There are three options to accomplish this.

### Use Power BI Premium

Assigning the app workspace to Power BI Premium capacity will allow the guest user to use the app without requiring a Power BI Pro license. Power BI Premium also allows for apps to take advantage of other capabilities like increased refresh rates, dedicated capacity and large model sizes.

![Use Power BI Premium](media/service-admin-azure-ad-b2b/license-approach1.png)

### Assign Power BI Pro license to guest user

Assigning a Power BI Pro license to the guest user, within your tenant, allows that guest user to view the content.

> [!NOTE]
> A Power BI Pro license from your tenant applies to guest users only when they access content within your tenant.

![Assign Pro license from your tenant](media/service-admin-azure-ad-b2b/license-approach2.png)

### Guest user brings their own Power BI Pro license

The guest user already has a Power BI Pro license assigned within their tenant.

![Guest user brings their own license](media/service-admin-azure-ad-b2b/license-approach3.png)

## Next steps

For more detailed information, including how row-level security works, check out the [whitepaper](https://aka.ms/powerbi-b2b-whitepaper).

For information regarding Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)