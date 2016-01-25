<properties 
   pageTitle="appFigures content pack"
   description="appFigures content pack for Power BI"
   services="powerbi" 
   documentationCenter="" 
   authors="theresapalmer" 
   manager="mblythe" 
   editor=""
   tags=""/>
 
<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="01/18/2016"
   ms.author="tpalmer"/>
   
# appFigures content pack for Power&nbsp;BI

Tracking important statistics about your apps is easy with Power BI and the appFigures content pack. Power BI retrieves your data, including app sales, downloads, and ad statistics, then builds a default dashboard and related reports based on that data.

Connect to the [appFigures content pack](https://app.powerbi.com/getdata/services/appfigures) for Power BI or read more about the [appFigures integration](https://powerbi.microsoft.com/en-us/integrations/appfigures).

## How to connect

1.  Select **Get Data** at the bottom of the left navigation pane.

	![](media/powerbi-content-pack-appfigures/PBI_GetData.png)

2.  In the **Services** box, select **Get**.

	![](media/powerbi-content-pack-appfigures/PBI_GetServices.png)

3.  Select **appFigures** \>  **Connect**.

	![](media/powerbi-content-pack-appfigures/appFigures.png)

4.  For **Authentication Method**, select **oAuth2** \> **Sign In**. When prompted, enter your appFigures credentials and follow the appFigures authentication process.

	The first time you connect, Power BI prompts you to allow read-only access to your account. Select **Allow** to begin the import process. This can take a few minutes depending on the volume of data in your account.

	![](media/powerbi-content-pack-appfigures/appFiguresDoc_06.png)

5. After Power BI imports the data you will see a new dashboard, report, and dataset in the left navigation pane. New items are marked with a yellow asterisk \*:

	![](media/powerbi-content-pack-appfigures/PBI_appFigures3.png)

6. Select the appFigures dashboard. This is the default dashboard that Power BI creates to display your data. You can modify this dashboard to display your data in any way you want.

	![](media/powerbi-content-pack-appfigures/appFiguresDoc_01.png)


**What Now?**

- Try [asking a question in the Q&A box](powerbi-service-q-and-a.md) at the top of the dashboard

- [Change the tiles](powerbi-service-edit-a-tile-in-a-dashboard.md) in the dashboard.

- [Select a tile](powerbi-service-dashboard-tiles.md) to open the underlying report.

- While your dataset will be schedule to refreshed daily, you can change the refresh schedule or try refreshing it on demand using **Refresh Now**


## What's included

The following data is available from appFigures in Power BI.


|**Table Name**|**Description**|
|---|---|
|Countries|This table provides country name information.|
|Dates|This table contains dates from today back to the earliest PublishDate of apps that are Active and Visible in your appFigures account.|
|Events|This table contains download, sales, and ad information for each app, by country, on a daily basis. Note that both app and in-app purchase information is all in this single table—you can use the <strong>Type</strong> column to differentiate.|
|Inapps|This table contains data about the different types of In-App Purchases that are associated with Active, Visible apps on your appFigures account.|
|Products|This table contains data about the different apps that are Active and Visible on your appFigures account.|

## Troubleshooting

If data from some of your apps is not showing up in Power BI, check to make sure that those apps are Visible and Active on the **apps** tab of the appFigures site.

![](media/powerbi-content-pack-appfigures/appFiguresDoc_11.png)

### See also

-  [Get started in Power BI](powerbi-service-get-started.md)
-  [Get data in Power BI](powerbi-service-get-data.md)

