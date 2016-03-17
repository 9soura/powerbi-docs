<properties 
   pageTitle="Zendesk content pack for Power BI"
   description="Zendesk content pack for Power BI"
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
   ms.date="03/16/2016"
   ms.author="tpalmer"/>
# Zendesk content pack for Power&nbsp;BI

The Zendesk content pack offers a Power BI dashboard and a set of Power BI reports that provide insights about your ticket volumes and agent performance. You can use the dashboard and reports provided, or customize them to highlight the information you care most about.  The data will be refreshed automatically once a day. 

Connect to the [Zendesk content pack](https://app.powerbi.com/getdata/services/zendesk) or read more about the [Zendesk integration](https://powerbi.microsoft.com/integrations/zendesk) with Power BI. 

Note: A Zendesk Admin account is required to connect. More details on requirements below.

## How to Connect

1.  Select **Get Data** at the bottom of the left navigation pane.

    ![](media/powerbi-content-pack-zendesk/PBI_GetData.png)

2.  In the **Services** box, select **Get**.

    ![](media/powerbi-content-pack-zendesk/PBI_GetServices.png) 

3.  Select **Zendesk** \> **Connect.**

    ![](media/powerbi-content-pack-zendesk/PBI_ZendeskConnect.png)

4.  Provide the URL associated with your account. This will be in the form **https://company.zendesk.com**, see details on [finding these parameters](#FindingParams) below.

	![](media/powerbi-content-pack-zendesk/PBI_ZendeskConnect.png)

5.  When prompted, enter your Zendesk credentials.  Select **oAuth 2** as the Authentication Mechanism and click **Sign In**. Follow the Zendesk authentication flow. Note that these credentials must be an Admin for your account.  (If you are already signed in to Zendesk in your browser, you may not be prompted for credentials.)

	![](media/powerbi-content-pack-zendesk/PBI_ZendeskSignIn.png)

6.  Click **Allow** to allow Power BI to access your Zendesk data.

	![](media/powerbi-content-pack-zendesk/zendesk2.jpg)

7.  Click **Connect** to begin the import process. After Power BI imports the data, you see a new dashboard, report, and dataset in the left navigation pane. New items are marked with a yellow asterisk \*.

	![](media/powerbi-content-pack-zendesk/PBI_ZendeskDash.png)

**What Now?**

- Try [asking a question in the Q&A box](powerbi-service-q-and-a.md) at the top of the dashboard

- [Change the tiles](powerbi-service-edit-a-tile-in-a-dashboard.md) in the dashboard.

- [Select a tile](powerbi-service-dashboard-tiles.md) to open the underlying report.

- While your dataset will be schedule to refreshed daily, you can change the refresh schedule or try refreshing it on demand using **Refresh Now**

## What's included

The Power BI content pack includes data on the following:
- Users (end users and agents)  
- Organizations  
- Groups  
- Tickets  

There's also a set of measures that have been calculated, such as Average Wait Time and Tickets Solved in the Last 7 days. A full list is included in the content pack. 

## System Requirements

A Zendesk Administrator account is required to access the Zendesk content pack. If you're an agent or an end user and are interested in viewing your Zendesk data, please add a suggestion and review the Zendesk connector in the [Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-connect-to-data/).

## Finding parameters 
<a name="FindingParams"></a>

Your Zendesk URL will be the same as the URL you use to sign into your Zendesk account. If you're not sure of your Zendesk URL, you can use the Zendesk [login help](https://www.zendesk.com/login/).

## Troubleshooting
If you are having issues connecting, please check your Zendesk URL and confirm you're using an Zendesk administrator account.

### See also
- [Get started with Power BI](powerbi-service-get-started.md)
- [Get data](powerbi-service-get-data.md)
