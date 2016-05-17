﻿<properties
   pageTitle="Lithium content pack for Power BI"
   description="Lithium content pack for Power BI"
   services="powerbi"
   documentationCenter=""
   authors="theresapalmer"
   manager="mblythe"
   backup=""
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
   ms.date="05/17/2016"
   ms.author="tpalmer"/>

# Lithium content pack for Power&nbsp;BI

Lithium builds trusted relationships between the world's best brands and their customers, helping people get answers and share their experiences. By connecting the Lithium content pack to Power BI, you can measure key metrics about your online community to help drive sales, reduce service costs and increase loyalty. 

Connect to the [Lithium content pack](https://app.powerbi.com/getdata/services/lithium) for Power BI.

Note: The Power BI content pack uses the Lithium API. Excessive calls to the API may result in additional charges from Lithium, please confirm with your Lithium administrator.

## How to connect
1.  Select **Get Data** at the bottom of the left navigation pane.

    ![](media/powerbi-content-pack-lithium/PBI_GetData.png) 

2.  In the **Services** box, select **Get**.

    ![](media/powerbi-content-pack-lithium/PBI_GetServices.png) 

3.  Select **Lithium** \> **Get**.

    ![](media/powerbi-content-pack-lithium/lithiumconnect.png)
    
4.  Provide the URL of your Lithium community. It will be in the form of *https://community.yoursite.com*.

    ![](media/powerbi-content-pack-lithium/params.png)

5.  When prompted, enter your Lithium credentials. Select **oAuth 2** as the Authentication Mechanism and click **Sign In** and follow the Lithium authentication flow.

    ![](media/powerbi-content-pack-lithium/creds.png)
    
    ![](media/powerbi-content-pack-lithium/creds2.png)

6.  Once the login flow is completed the import process will begin. When complete, a new dashboard, report and model will appear in the Navigation Pane. Select the dashboard to view your imported data.

     ![](media/powerbi-content-pack-lithium/lithium.png)

**What Now?**

- Try [asking a question in the Q&A box](powerbi-service-q-and-a.md) at the top of the dashboard

- [Change the tiles](powerbi-service-edit-a-tile-in-a-dashboard.md) in the dashboard.

- [Select a tile](powerbi-service-dashboard-tiles.md) to open the underlying report.

- While your dataset will be schedule to refreshed daily, you can change the refresh schedule or try refreshing it on demand using **Refresh Now**

## System requirements

The Lithium content pack requires a Lithium community v15.9 or greater. Please check with your Lithium admin to confirm.

### See also

[Get started with Power BI](powerbi-service-get-started.md)

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)
