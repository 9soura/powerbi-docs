<properties
   pageTitle="Power BI get started with third party apps"
   description="Power BI get started with third party apps"
   services="powerbi"
   documentationCenter=""
   authors="dvana"
   manager="mblythe"
   editor=""
   tags=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="12/17/2015"
   ms.author="derrickv"/>

# Get started with third party apps

With Power BI, you can use an app built by a company or individual other than Microsoft. For example, you might use a third party app which integrates Power BI tiles into a custom built web application. When you use a third party app, you will be asked to grant that application certain permissions to your Power BI account and content. It is important that you only grant permissions to applications that you know and trust. Permissions to an application can be revoked at any time. See [Revoke third party app permissions](#revoke).

Here are the types of access an application can request.

## Power BI App permissions

-	**View all Dashboards (preview)**

  - This permission gives an application the ability to list out and view all dashboards you have access to. This includes dashboards that you own, have gotten from content packs, and have been shared to you and are in groups that you belong to. The application cannot make any modifications to the dashboard itself. Among other things, this permission can be used by an application to embed your dashboard content into its experiences.

-	**View all Reports (preview)**

  - This permission gives an application the ability to list out and view all the reports you have access to. This includes reports that you own, have gotten from content packs, and are in groups that you belong to. Part of viewing the report, means that the application can also see the data within it. The application cannot make any modifications to the reports themselves. Among other things, this permission can be used by an application to embed your report content into its experiences.

-	**View all Datasets**

  - This permission gives an application the ability to list out all datasets that you have access to. This includes reports that you own, have gotten from content packs, and are in groups that you belong to. An application can see the names of all your datasets as well as their structure including table and column names. Currently there are no features that allow an application to see the data within the dataset, but this may change over time.  The permission does not give the application to add or make any changes to a dataset.

-	**Read and Write all Datasets**

  - This permission gives an application the ability to list all datasets that you have access to. This includes reports that you own, have gotten from content packs, and are in groups that you belong to. An application can see the names of all your datasets as well as their structure including table and column names. Currently there are no features that allow and application to see the data within the dataset, but this may change over time. The application can also create new dataset, make modifications to existing ones, or update the data within. This is commonly used by application that wish to send to data directly to Power BI.

-	**View user's Groups**

  -  This permission gives the application the ability to list all groups that you are a member of. It can then use this permission along with some of the other permissions listed to view or update content for that particular group. The application cannot make modifications to the group itself.

<a name="revoke"/>
## Revoke third party app permissions

You revoke permissions for a third party app by going to the Office 365 My Apps site.

On the **Office 365 My apps** site, here's how to revoke third party permissions:

1. Go to [Office 365 My Apps site](https://portal.office.com/myapps).
2. On the **My apps** page, locate the third party app.
3. Hover over the app tile, click the **(...)** button, and click **Remove**.

  ![](media/powerbi-service-power-bi-get-started-third-party-apps/remove.png)
