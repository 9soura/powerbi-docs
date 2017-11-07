---
title: Connect to Webtrends with Power BI
description: Webtrends for Power BI
services: powerbi
documentationcenter: ''
author: joeshoukry
manager: erikre
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''

ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry

---
# Connect to Webtrends with Power BI
The Webtrends content pack for Power BI includes a variety of out of box metrics such total page views and visits by traffic source. Visualizing your Webtrends data in Power BI starts by connecting to your Webtrends account. You can use the dashboard and reports provided, or customize them to highlight the information you care most about.  The data will be refreshed automatically once per day.

Connect to the [Webtrends content pack for Power BI.](https://app.powerbi.com/getdata/services/webtrends)

## How to connect
1. Select **Get Data** at the bottom of the left navigation pane.
   
   ![](media/powerbi-content-pack-webtrends/getdata3.png)
2. In the **Services** box, select **Get**.
   
   ![](media/powerbi-content-pack-webtrends/services.PNG)
3. Select **Webtrends** \> **Get**.
   
   ![](media/powerbi-content-pack-webtrends/webtrends.png)
4. The content pack connects to a specific Webtrends profile ID. See details on [finding this parameter](#FindingParams) below.
   
   ![](media/powerbi-content-pack-webtrends/parameters.PNG)
5. Provide your Webtrends credentials to connect. Note that the username field expects your account and username. See [details](#FindingParams) below.
   
   ![](media/powerbi-content-pack-webtrends/creds.PNG)
6. After approving, the import process will begin automatically. When complete, a new dashboard, report and model will appear in the Navigation Pane. Select the dashboard to view your imported data.
   
   ![](media/powerbi-content-pack-webtrends/dashboard.PNG)

**What Now?**

* Try [asking a question in the Q&A box](powerbi-service-q-and-a.md) at the top of the dashboard
* [Change the tiles](powerbi-service-edit-a-tile-in-a-dashboard.md) in the dashboard.
* [Select a tile](powerbi-service-dashboard-tiles.md) to open the underlying report.
* While your dataset will be schedule to refreshed daily, you can change the refresh schedule or try refreshing it on demand using **Refresh Now**

## What's included
<a name="Included"></a>

The Webtrends content pack pulls data from the following reports:  

| Report Name | Report ID |
| --- | --- |
| Key Metrics | |
| On-Site Searches |34awBVEP0P6 |
| Exit Pages |7FshY8eP0P6 |
| Next Pages |CTd5rpeP0P6 |
| Previous Pages |aSdOeaUgnP6 |
| Site Pages |oOEWQj3sUo6 |
| Onsite Ads Clickthroughs |41df19b6d9f |
| Cities |aUuHskcP0P6 |
| Countries |JHWXJNcP0P6 |
| Visitors |xPcmTDDP0P6 |
| Visit Duration |U5KAyqdP0P6 |
| Search Phrases |IKYEDxIP0P6 |
| Traffic Sources |JmttAoIP0P6 |
| Search Engines |yGz3gAGP0P6 |
| Entry Pages |i6LrkNVRUo6 |

Note: For SharePoint profiles, the metric names may be a little different than what's show in the Webtrends UI. The following mapping is done to maintain consistency between SharePoint and Web profiles:   

    - Sessions = Visits  
    - New Users = New Visitors  
    - Views per Session = Page Views per Visit  
    - Avg Daily User Duration = Avg Time on Site per Visitor  

## System requirements
The content pack requires access to a Webtrends profile with the [correct set of reports](#Included) enabled.

<a name="FindingParams"></a>

## Finding parameters
Your Webtrends Profile ID can be found in the URL after you've selected a profile:

![](media/powerbi-content-pack-webtrends/WebtrendsParameters.png)

Your credentials are the same as what you enter when you sign into Webtrends, however we expect your account and username in the same line, separated by a backslash:

![](media/powerbi-content-pack-webtrends/WebtrendsCreds.PNG)

## Troubleshooting
You may hit an issue while the content pack is loading, after you've provided your credentials. If you see the "Oops" message during the loading, please review the troubleshooting suggestions below. If you're still having issues please file a support ticket at https://support.powerbi.com

1. The correct Profile ID is being used, see the [Finding Parameters](#FindingParams) for more details.
2. The user has access to the reports listed in the ["What's included"](#Included) section

### See also
[Get started with Power BI](powerbi-service-get-started.md)

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

