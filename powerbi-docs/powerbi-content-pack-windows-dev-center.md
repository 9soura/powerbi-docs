---
title: Connect to Windows Dev Center with Power BI
description: Windows Dev Center for Power BI
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
# Connect to Windows Dev Center with Power BI
Explore and monitor your Windows Dev Center app analytics data in Power BI with the Power BI content pack. The data will be refreshed automatically once per day.

Connect to the [Windows Dev Center content pack](https://app.powerbi.com/getdata/services/devcenter) for Power BI.

## How to connect
1. Select **Get Data** at the bottom of the left navigation pane.
   
   ![](media/powerbi-content-pack-windows-dev-center/getdata.png)
2. In the **Services** box, select **Get**.
   
   ![](media/powerbi-content-pack-windows-dev-center/services.PNG)
3. Select **Windows Dev Center** \>  **Get**.
   
   ![](media/powerbi-content-pack-windows-dev-center/windowsdev.png)
4. Enter the application ID of an app you own and click Next. See details on [finding those parameters](#FindingParams) below.
   
   ![](media/powerbi-content-pack-windows-dev-center/params.png)
5. For **Authentication Method**, select **oAuth2** \> **Sign In**. When prompted, enter your Azure Active Directory credentials associated with your Windows Dev Center account (more details in [System Requirements](#Requirements)).
   
    ![](media/powerbi-content-pack-windows-dev-center/creds.png)
   
    ![](media/powerbi-content-pack-windows-dev-center/creds2.png)
6. After approving, the import process will begin automatically. When complete, a new dashboard, report and model will appear in the Navigation Pane. Select the dashboard to view your imported data and choose a tile to navigate to the underlying reports.
   
    ![](media/powerbi-content-pack-windows-dev-center/dashboard.png)
   
    ![](media/powerbi-content-pack-windows-dev-center/report.png)

**What Now?**

* Try [asking a question in the Q&A box](powerbi-service-q-and-a.md) at the top of the dashboard
* [Change the tiles](service-dashboard-edit-tile.md) in the dashboard.
* [Select a tile](powerbi-service-dashboard-tiles.md) to open the underlying report.
* While your dataset will be schedule to refreshed daily, you can change the refresh schedule or try refreshing it on demand using **Refresh Now**

## What's included
The Dev Center Power BI content pack includes analytics data for your app and IAP acquisitions, ratings, reviews and app health. Data is limited to the last 3 months. and is a moving window, so the dates included will update as the dataset refreshes.

<a name="Requirements"></a>

## System requirements
This content pack requires at least one at least one app published to the Windows Store and a Windows Dev Center account (more details [here](https://msdn.microsoft.com/windows/uwp/publish/manage-account-users)).

<a name="FindingParams"></a>

## Finding parameters
You can find the application ID for an app by going to the App identity page under App management.

The application ID is on the end of your URL for Windows 10 Store, https://www.microsoft.com/store/apps/ **{applicationId}**

### See also
[Get started in Power BI](powerbi-service-get-started.md)

[Get data in Power BI](service-get-data.md)

