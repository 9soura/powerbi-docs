﻿<properties 
   pageTitle="Work with organizational content packs"
   description="Work with organizational content packs"
   services="powerbi" 
   documentationCenter="" 
   authors="maggiesMSFT" 
   manager="mblythe" 
   editor=""
   tags=""/>
 
<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/14/2015"
   ms.author="maggies"/>
# Work with organizational content packs

When an organizational content pack is published, all members see the same dashboard, reports, and datasets (unless it's an SSAS data source).  [Only the creator can edit and republish](powerbi-service-organizational-content-packs-manage-update-delete.md%0A) the content pack.  However, all users can customize the dashboards and reports, and when those changes are saved, a new *personalized* version of the content pack replaces the original.

## Edit an organizational content pack:

Editing and saving changes to an organizational content pack create a new version of the content pack.  This personalized version is not visible to others.

1.  Open the content pack and make a change.  Power BI lets you know that if you save this change you'll create a personal copy of the content pack. 

     ![](media/powerbi-service-organizational-content-packs-use-and-work-with/personalize.png)

2.  Select **Save**.  



## Help!  I can no longer access the content pack

This can happen for several reasons:

-   Membership changes:  Content packs are published to email aliases.  If you are removed from that alias, you will no longer have access to the content pack. Aliases can be based on security groups, distribution groups, and Office 365 groups.

-   Distribution changes: The content pack creator changes the distribution. For example, the content pack was originally published to the entire organization but the creator republished it to a smaller audience and you are no longer included.

-   Security settings changes: If the dashboard and reports connect to on-premises SSAS data sources and changes are made to the security settings, your permissions to that server may be revoked.

## How are organizational content packs refreshed?

When the content pack is created, the refresh settings are inherited with the dataset.  When a group member creates a new personal version of the content pack, the link to the original dataset, and its refresh schedule, is retained. 

See [Managing, updating, and deleting organizational content packs](powerbi-service-organizational-content-packs-manage-update-delete.md).

## See Also:

[Introduction to organizational content packs](powerbi-service-organizational-content-packs-introduction.md)

[Get Started with Power BI](powerbi-service-get-started.md)

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

[Groups in Power BI](powerbi-service-groups.md)

