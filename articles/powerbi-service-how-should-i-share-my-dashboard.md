<properties
   pageTitle="How should I collaborate on & share dashboards and reports?"
   description="In Power BI you can collaborate on and share dashboards, reports, and tiles in several different ways. Each has its advantages."
   services="powerbi"
   documentationCenter=""
   authors="ajayan"
   manager="erikre"
   backup="maggiesMSFT"
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="02/28/2017"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="04/28/2017"
   ms.author="ajayan"/>

# How should I collaborate on & share dashboards and reports?  

You create dashboards and reports yourself. Sometimes you want to collaborate on them with your colleagues, and then you want others to have access to them, too. What's the best way to distribute them?

In this article, we'll talk about options for collaborating and sharing in Power BI: collaborating with colleagues to create meaningful reports and dashboards; distributing them to a larger group or your whole organization; sharing dashboards from the service or the Power BI mobile apps; publishing to the web; and printing. 

![](media/powerbi-service-how-should-i-share-my-dashboard/power-bi-apps-home-blog.png)

*Apps in the Power BI service*

When the reports and dashboards are ready, if you want other people to access them you have options for how to do that. For example:

- You can *share* them, either from the Power BI service or from one of the Power BI mobile apps. 
- You can bundle them into an *app* and publish them to a large group or to your whole organization. 
- You can even publish them to the web, where anyone can interact with them. 

This article compares these and other activities.

> [AZURE.NOTE] In most cases, the people you collaborate and share with need [Power BI free or Pro](https://powerbi.microsoft.com/) licenses before they can see your dashboards and reports. 

## Collaborate with colleagues to create an app, with dashboards and reports

Say you and your teammates want to create a collection of dashboards and reports for your organization. The best way to do that is to create an *app*. An app is a collection of dashboards and reports purpose-built by your organization to deliver key metrics for faster and easier data-driven decisions. Apps are easy to find and install in the Power BI service ([https://powerbi.com](https://powerbi.com)). After you install them, you can view them in your browser or mobile device.

To create an app, you need a *app workspace*, with your teammates as members. Think of the app workspace as a place where you and they can collaborate on your Power BI dashboards and reports. All of you can create reports in Power BI Desktop and publish those reports to the app workspace. You can give everyone in the workspace the same permissions, or you can give some members just read-only permissions.

![](media/powerbi-service-how-should-i-share-my-dashboard/power-bi-apps-workspaces.png)

**If you just want to share a finished dashboard with colleagues, don't add those colleagues to the app workspace.** 

Instead, [create the app in an app workspace, and distribute it](powerbi-service-create-apps.md). 

## Share a dashboard with others 
Let's say you've finalized a dashboard in your own My Workspace or in an app workspace and you want others have access to it. One way to get it to them is to *share* it. Sharing has a specific meaning in Power BI. 

![](media/powerbi-service-how-should-i-share-my-dashboard/power-bi-service-share.png)

When you share a dashboard, those you share it with can view it and interact with it, but can't edit it. They see the same data that you see in the dashboard and reports unless row-level security (RLS) is applied to the underlying dataset. The colleagues you share it with can share the dashboard with their colleagues, if you allow them to. 

You can share dashboards to Active Directory security groups, or to your entire organization, and you can share with people outside your organization. They can view and interact with the dashboard too, but can't share it. More about [sharing a dashboard from the Power BI service](powerbi-service-share-unshare-dashboard.md).

> [AZURE.NOTE] You can't share with dynamic distribution lists.

You can also [share a dashboard from any of the Power BI mobile apps](powerbi-mobile-share-a-dashboard-from-the-iphone-app.md). 

### Share a dashboard with colleagues outside an app workspace 
If you're part of an app workspace in Power BI, you can share the dashboards with colleagues outside the app workspace. It's the same as [sharing a dashboard with colleagues](powerbi-service-share-unshare-dashboard.md).

## Create an app and publish it  
Another way to distribute your Power BI insights with your colleagues is to create an *app*. You've created and refined a dashboard with its reports and datasets, either in your own My Workspace or in an app workspace. Now you bundle them together as an app and distribute them &#151; either to members of an Active Directory security group or distribution list, or to your whole organization. 

> [AZURE.NOTE] You can't share with dynamic distribution lists.

![](media/powerbi-service-how-should-i-share-my-dashboard/cpwindow.png)

When those colleagues go to the Microsoft AppSource for your organization, they see your app along with any others that have been distributed to them. More about [apps](powerbi-service-what-are-apps.md).  

## Annotate and share from the Power BI mobile apps
In the Power BI mobile apps for iOS and Android devices, you can annotate a tile, report, or visual and then share it with anyone via email. 

![](media/powerbi-service-how-should-i-share-my-dashboard/power-bi-iphone-annotate.png)

You're sharing a snapshot of the tile, report, or visual, and your recipients see it exactly as it was when you sent the mail. The mail also contains a link to the dashboard or report, and if you've shared that with them already, they can open it. You can send snapshots of tiles to anyone &#151; not just colleagues in the same email domain.

More about [annotating and sharing tiles, reports, and visuals](powerbi-mobile-annotate-and-share-a-tile-from-the-iphone-app.md) from the iOS and Android mobile apps.

You can also share a snapshot of a tile from the [Power BI app for Windows 10 devices](powerbi-mobile-annotate-and-share-a-snapshot-from-the-windows-app.md).

## Publish to the web

You can publish Power BI reports to the whole Internet by embedding interactive visualizations in blog posts, websites, social media, and other online communications on any device. Anyone on the Internet can view your reports, and you have no control over who can see what you've published. They don't need a Power BI license. Publishing to the web is available only for reports in your My Workspace that you can edit. If someone shares a report with you, you can't publish it to the web. More about [publishing to the web](powerbi-service-publish-to-web.md).


## Print or save as PDF or other static file

You can print or save as PDF (or other static file format) an entire dashboard, dashboard tile, report page, or visualization from the Power BI service. Reports can only be printed one page at a time -- you can't print the entire report at once. More about [printing or saving as a static file](powerbi-service-print.md).

## Next steps
-   [Share a dashboard with colleagues](powerbi-service-share-unshare-dashboard.md)
-   [Create and distribute an app in Power BI](powerbi-service-create-apps.md)
-   More questions? [Try the Power BI Community](http://community.powerbi.com/).



