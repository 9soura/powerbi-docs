---
title: Organize work in the new workspaces (preview) - Power BI
description: Learn how to create the new workspaces, collections of dashboards and reports built to deliver key metrics for your organization.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/29/2019
ms.author: maggies

LocalizationGroup: Share your work
---
# Organize work in the new workspaces in Power BI

Workspaces are places to collaborate with colleagues to create collections of dashboards and reports. You can bundle those collections into *apps* with their own table of contents. Then you can distribute them to your whole organization or to specific people or groups. Power BI is introducing a new workspace experience to better help you manage access to content in workspaces. 

The new workspace experience has reached GA is now the default workspace experience. You can continue to create and use existing classic workspaces that are based on Offie 365 Groups. 

With the new workspaces, you can:

- Assign workspace roles to user groups: security groups, distribution lists, Office 365 groups, and individuals.
- Create a workspace in Power BI without creating an Office 365 group.
- Use more granular workspaces roles for more flexible permissions management in a workspace.

Read about how to [create one of the new workspaces](service-create-the-new-workspaces.md).

> [!NOTE]
> To enforce row-level security (RLS) for users browsing content in a workspace, continue to use classic workspaces and select the **Members can only view Power BI content** option. Alternatively, publish a Power BI app to the users. 

When you create one of the new workspaces, you're not creating an underlying, associated Office 365 group. All the workspace administration is in Power BI, not in Office 365. You can still add an Office 365 group to the workspace to continue managing user access to content through Office 365 groups. However, you can additionally use security groups, distribution lists, and add individuals directly within Power BI, giving you a flexible way to manage workspace access. Because workspace administration is now in Power BI, Power BI admins decide who in an organization can create workspaces. In **Workspace settings** in the admin portal, admins can allow everybody or nobody in an organization to create workspaces. They can also limit creation to members of specific security groups.

![Workspace settings in the admin portal](media/service-new-workspaces/power-bi-workspace-admin-settings.png)

Read more about the [Power BI admin portal](service-admin-portal.md).

## New workspaces side by side with classic workspaces

New, upgraded workspaces, and existing classic workspaces coexist side by side, and you can create either. The new workspace experience is the default workspace type. To learn how to create a new workspace, read [Create new workspaces](service-create-the-new-workspaces.md). To learn how to create a classic workspace, read [Create the classic workspaces](service-create-workspaces.md).

## Roles in the new workspaces

You add user groups or individuals to the new workspaces as members, contributors, or admins. Everyone in a user group gets the role you’ve defined. If an individual is in several user groups, they get highest level of permission provided by the role.

Everyone you add to a workspace needs a Power BI Pro license. In the workspace, these users can all collaborate on dashboards and reports that you plan to publish to a wider audience, or even to your entire organization. If you want to distribute content to others inside your organization, you can assign Power BI Pro licenses to those users or place the workspace in a Power BI Premium capacity.

Roles let you manage who can do what in a workspace, so teams can collaborate. New workspaces allow you to assign roles to individuals, and to user groups: security groups, Office 365 groups, and distribution lists. 

When you assign roles to a user group, the individuals in the group have access to content. If you nest user groups, all the contained users have permission. A user who's in several user groups with different roles gets the highest level of permission granted them. 

The new workspaces offer three roles: admins, members, and contributors.

|Capability   | Admin  | Member  | Contributor  | 
|---|---|---|---|
| Update and delete the workspace.  | X  |   |   |
| Add/remove people, including other admins.  | X  |   |   |
| Add members or others with lower permissions.  |  X | X  |   |
| Publish and update an app. |  X | X  |   |
| Share an item or share an app. |  X | X  |   |
| Allow others to reshare items. |  X | X  |   |
| Create, edit, and delete content in the workspace.  |  X | X  | X  |
| Publish reports to the workspace, delete content. |  X | X  | X  |
 

## How are the new workspaces different from current workspaces?

With the new workspaces, we're redesigning some features. Here are the changes you can expect to be permanent along with the preview. 

* Creating workspaces won't create corresponding entities in Office 365 like current workspaces do. (You can still add an Office 365 group to your workspace by assigning it a role). 
* In classic workspaces, you can add only individuals to the members and admin lists. In the new workspaces, you can add multiple AD security groups, distribution lists, or Office 365 groups to these lists to allow for easier user management. 
- You can create an organizational content pack from a classic workspace. You can't create one from the new workspaces.
- You can consume an organizational content pack from a classic workspace. You can’t consume one from the new workspaces.

## Workspace contact list
The new contact list feature available in workspace settings or under advanced when creating workspaces allows you to specify which users receive notification about issues occurring in the workspace. By default, any user or group specified as a workspace admin is notified, but you can customize the list. Just be aware that users or groups listed in the contact list will be shown in UI experiences in the future to help users get help related to the workspace. 

## Workspace OneDrive
The Workspace OneDrive feature allows you to configure an existing Office 365 Group whose OneDrive file storage will be available to workspace users. The location will appear under Files in the “…” menu on the workspace.  Note that Power BI doesn't synchronize permissions of users / groups who are configured to have workspace access with the Office 365 Group membership. The best practice is to ensure you manage workspace access through the same Office 365 Group whose OneDrive you configure in this setting.

It will also appear in the Get Data > Files experience. The OneDrive – Business entry is the current user’s OneDrive for Business.

## Limitations and considerations

Limitations to be aware of:

- Workspaces can contain a maximum of 1,000 datasets, or 1,000 reports per dataset. 
- A person with a Power BI Pro license can be a member of a maximum 250 workspaces.
- Power BI publisher for Excel is not supported.

## Workspace features that work differently

Some features work differently from current workspaces in the new workspaces. These differences are intentional, based on feedback we’ve received from customers, and will enable a more flexible approach to collaboration with workspaces:

- Licensing enforcement: Publishing reports to new workspace experience enforces existing licensing rules that require a Power BI Pro license for users collaborating in workspaces or sharing content to others in the Power BI service. Users without a Pro license will see the error "Only users with Powre BI Pro licenses can publish to this workspace."
- Members can or can't reshare: replaced by the Contributor role
- Read-only workspaces: Instead of granting users read-only access to a workspace, you'll assign users to a forthcoming Viewer role, which allows similar read-only access to the content in a workspace.
- No **Leave workspace** button.

## Frequently Asked Questions

**Will links to existing content be affected by the new workspace experience GA**

No. Links to existing items in classic workspaces are not affected by the new workspace experience. The GA of new workspace experience changes the default workspace that is created, but does not change existing workspaces. 

**Are existing workspaces upgraded to the new workspace experience with GA**

No. The new workspace experience GA only change the default workspace type to the new workspace experience. Existing classic workspaces that are based on Office 365 Groups remain unchanged.

**Are workspaces still automatically created for Office 365 Groups**

Yes. Since we support both types of workspaces side by side, we continue to list all Office 365 Groups the user has access to in the worksapces list.

**How will the announced Viewer role work**

The Viewer role will give read-only access to workspace content. Users with Read-only access will have Row Level Security (RLS) enforced. The Viewer role will become available at after GA.


## Next steps
* [Create the new workspaces in Power BI](service-create-the-new-workspaces.md)
* [Create the classic workspaces](service-create-workspaces.md)
* [Install and use apps in Power BI](service-create-distribute-apps.md)
* Questions? [Try asking the Power BI Community](http://community.powerbi.com/)
