---
title: Connect to SparkPost with Power BI
description: SparkPost for Power BI
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
# Connect to SparkPost with Power BI
The Power BI content pack for SparkPost allows you to extract valuable datasets from your SparkPost account all into one insightful dashboard. Using the SparkPost content pack you can visualize your overall email statistics, including domains, campaigns, and engagement by ISP.

Connect to the [SparkPost content pack for Power BI](https://app.powerbi.com/getdata/services/spark-post).

## How to connect
1. Select **Get Data** at the bottom of the left navigation pane.
   
   ![](media/powerbi-content-pack-sparkpost/getdata.png)
2. In the **Services** box, select **Get**.
   
   ![](media/powerbi-content-pack-sparkpost/services.PNG)
3. Select the **SparkPost** content pack and click **Get**. 
   
   ![](media/powerbi-content-pack-sparkpost/sparkpost.png)
4. When prompted, provide your SparkPost API key and select Sign In. See details on [finding this parameters](#FindingParams) below.
   
   ![](media/powerbi-content-pack-sparkpost/Creds.PNG)
5. Your data will start to load, depending on the size of you account this may take some time. After Power BI imports the data, you’ll see the default dashboard, report, and dataset in the left navigation pane, populated with your email statistics for the past 90 days. New items are marked with a yellow asterisk \*.
   
   ![](media/powerbi-content-pack-sparkpost/dashboard.PNG)

**What Now?**

* Try [asking a question in the Q&A box](powerbi-service-q-and-a.md) at the top of the dashboard
* [Change the tiles](powerbi-service-edit-a-tile-in-a-dashboard.md) in the dashboard.
* [Select a tile](powerbi-service-dashboard-tiles.md) to open the underlying report.
* While your dataset will be schedule to refreshed daily, you can change the refresh schedule or try refreshing it on demand using **Refresh Now**

## What's included
The SparkPost content pack for Power BI includes information including unique clicks, accepted rates, bounce rates, delayed rates, rejection rates and more.

<a name="FindingParams"></a>

## Finding parameters
The content pack uses an API key to connect your SparkPost account to Power BI. You can find your API key in your account under Account \> API & SMTP (more details [here](https://support.sparkpost.com/customer/portal/articles/1933377-create-api-keys)). We suggest using an API key with permissions for `Message Events: Read-only `and `Metrics: Read-only`

![](media/powerbi-content-pack-sparkpost/SparkPost1.png)

