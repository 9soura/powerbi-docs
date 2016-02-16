﻿<properties
   pageTitle="Twilio content pack for Power BI"
   description="Twilio content pack for Power BI"
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
   ms.date="02/08/2016"
   ms.author="tpalmer"/>

# Twilio content pack for Power&nbsp;BI

The Microsoft Twilio content pack for Power BI allows you to pull your data into Power BI and creates an out of box [Twilio dashboard](https://powerbi.microsoft.com/en-us/integrations/twilio) and report that shows insights on your data. You can also create your custom reports and dashboard on the dataset Power BI creates. The data will be refreshed once a day so you are always looking at the latest data.

Connect to the [Twilio content pack](https://app.powerbi.com/getdata/services/twilio) for Power BI.

1.  Select **Get Data** at the bottom of the left navigation pane.

    ![](media/powerbi-content-pack-twilio/PBI_GetData.png) 

2.  In the **Services** box, select **Get**.

    ![](media/powerbi-content-pack-twilio/PBI_GetServices.png) 

3.  Select **Twilio** \> **Connect**.

    ![](media/powerbi-content-pack-twilio/PBI_TwilioConnect.png)

4.  For **Authentication Method**, select **oAuth2** \> Sign In.

5.  When prompted provide your Twilio credentials and authorize the Power BI application to access your data.

    ![](media/powerbi-content-pack-twilio/PBI_Twilio_Login.PNG)


6.  This will begin importing data from your Twilio account, and you will have your dashboard populated with your calls and messages usage for the past 30 days. 

    ![](media/powerbi-content-pack-twilio/PBI_Twilio_DB.png)

This dashboard can be fully changed to how you want to display your data. It allows you to ask a [question in ](powerbi-service-q-and-a.md)[Q&A](powerbi-service-q-and-a.md) or click a tile to [open the underlying report](powerbi-service-dashboard-tiles.md) and [c](powerbi-service-edit-a-tile-in-a-dashboard.md)[](powerbi-service-edit-a-tile-in-a-dashboard.md)[hange the tiles](powerbi-service-edit-a-tile-in-a-dashboard.md) in the dashboard. 

**The data that the content pack brings from Twilio**

1.  The details for all calls and messages transactions for the last 30 days. You can do all sorts of analysis and aggregation on this data.

2.  A set of already aggregated stats that you may want to keep an eye on. This set includes:

All Time Calls Count  
All Time Calls Duration  
All Time Calls Price  
All Time Messages Price  
All Time Messages Count  
All Time Count of Phone Numbers  
All Time Price of Phone Numbers  
All Time Twilio Client Calls Price  
All Time Twilio Client Calls Duration  
All Time Twilio Client Calls Count  
All Time Total Price  
All Time Inbound Calls Price  
All Time Inbound Calls Duration  
All Time Inbound Calls Count  
All Time Outbound Calls Price  
All Time Outbound Calls Duration  
All Time Outbound Calls Count  
This Month Calls Price  
This Month Calls Duration  
This Month Calls Count  
This Month Messages Count  
This Month Messages Price  
This Month Count of Phone Numbers  
This Month Price of Phone Numbers  
This Month Twilio Client Calls Price  
This Month Twilio Client Calls Duration  
This Month Twilio Client Calls Count  
This Month Total Price  
This Month Inbound Calls Price  
This Month Inbound Calls Duration  
This Month Inbound Calls Count  
This Month Outbound Calls Price  
This Month Outbound Calls Duration  
This Month Outbound Calls Count  
This Month Inbound Messages Price  
This Month Inbound Messages Count  
This Month Outbound Messages Price  
This Month Outbound Messages Count

**Known Issues**

If you have a very large amount of data in the past 30 days (hundreds of thousands of transactions), the data retrieval step might fail. We are aware of the problem and working on solving it. Meanwhile, if you hit this issue please use the support link at the top of your Power BI page to let us know and we'll contact you for further investigations.
