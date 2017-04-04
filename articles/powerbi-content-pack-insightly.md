<properties
   pageTitle="Insightly content pack"
   description="Insightly content pack for Power BI"
   services="powerbi"
   documentationCenter=""
   authors="joeshoukry"
   manager="erikre"
   backup="maggiesMSFT"
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="03/10/2017"
   ms.author="yshoukry"/>
# Insightly content pack for Power&nbsp;BI

Visualize and share your Insightly CRM data in Power BI with the Insightly content pack. Connect to Power BI using your Insightly API key to view and build reports and dashboards from your CRM data. With Power BI, you can analyze your data in new ways, create powerful graphs and charts, and display contacts, leads, and organizations on a map.

Connect to the [Insightly content pack](https://app.powerbi.com/getdata/services/insightly) for Power BI.

## How to connect

1.  Select **Get Data** at the bottom of the left navigation pane.

	![](media/powerbi-content-pack-insightly/getdata.png)

2.  In the **Services** box, select **Get**.

	![](media/powerbi-content-pack-insightly/services.png)

3.  Select **Insightly** \>  **Get**.

	![](media/powerbi-content-pack-insightly/insightly.png)

4.  Select **Key** as the Authentication type and provide your Insight API Key then select **Sign In**. See details on [finding this](#FindingParams) below.

	![](media/powerbi-content-pack-insightly/creds.png)

5. After approving, the import process will begin automatically. When complete, a new dashboard, report and model will appear in the Navigation Pane. Select the dashboard to view your imported data.

	 ![](media/powerbi-content-pack-insightly/dashboard.png)


**What Now?**

- Try [asking a question in the Q&A box](powerbi-service-q-and-a.md) at the top of the dashboard

- [Change the tiles](powerbi-service-edit-a-tile-in-a-dashboard.md) in the dashboard.

- [Select a tile](powerbi-service-dashboard-tiles.md) to open the underlying report.

- While your dataset will be schedule to refreshed daily, you can change the refresh schedule or try refreshing it on demand using **Refresh Now**

## What's included

The content pack includes the following tables with fields from the corresponding records:

|Tables | | | |
|---|---|---|---|
| Contacts | Opportunities | Pipeline Stages | Task Complete Date |  
|Custom Fields|Opportunity Close Date|Project Complete Date|Tasks|  
|Events|Opportunity Forecast Date|Projects|Teams/Members|  
|Leads|Organizations|Tags|Users|  

Many tables and reports also include unique calculated fields, such as:  
- Tables with “grouped” opportunity forecast close dates, opportunity actual close dates, project completion dates, and task completion dates for analysis by month, quarter, or year.  
- A weighted value field for opportunities (opportunity value * probability of winning).  
- Average and total duration fields for tasks, based on start and completed dates.  
- Reports with calculated fields for opportunity win rate (count of won/count of total opportunities) and win rate value (value of won/value of total opportunities).  

## System requirements

An Insightly account with access to the Insightly API is required. Visibility permissions will be based on the API key used to establish the connection to Power BI. Any Insightly records visible to you will also be visible in the Power BI reports and dashboards that you share with others.

<a name="FindingParams"></a>
## Finding parameters

**API Key**

To copy your API key from Insightly, select User Settings from the Insightly profile menu and scroll down. This string of characters will be used to connect your data to Power BI.

![](media/powerbi-content-pack-insightly/findapi.png)

## Troubleshooting

Your data is imported via the Insightly API, which includes a daily limit based on your Insightly subscription plan level. The limits are listed in the Rate Limiting/Throttling Requests section of our API documentation: https://api.insight.ly/v2.2/Help#!/Overview/Introduction#ratelimit

The provided reports use default fields from Insightly and may not include your customizations. Edit the report to view all the available fields.

### See also

[Get started in Power BI](powerbi-service-get-started.md)

[Get data in Power BI](powerbi-service-get-data.md)
