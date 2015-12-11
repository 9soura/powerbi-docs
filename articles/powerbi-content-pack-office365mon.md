﻿<properties 
   pageTitle="Office365Mon content pack for Power BI"
   description="Office365Mon content pack for Power BI"
   services="powerbi" 
   documentationCenter="" 
   authors="tpalmer" 
   manager="mblythe" 
   editor=""
   tags=""/>
 
<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/28/2015"
   ms.author="maggies"/>
# Office365Mon content pack for Power BI

Analyzing your Office 365 outages and health performance data is easy with Power BI and the Office365Mon content pack. Power BI retrieves your data, including outages and health probes, then builds an out-of-box dashboard and reports based on that data.

**Important:**

-   An Office365Mon admin account is required to connect and load the Power BI content pack

Connect to the [Office365Mon content pack](https://app.powerbi.com/groups/me/getdata/services/) for Power BI.



1.  Select **Get Data** at the bottom of the left navigation pane.

	![](media/powerbi-content-pack-office365mon/PBI_GetData.png)

2.  In the **Services** box, select **Get**.

	![](media/powerbi-content-pack-office365mon/PBI_GetServices.png) 

3.  Select **Office365Mon \> Connect**.

	![](media/powerbi-content-pack-office365mon/connect.png)

4.  For Authentication Method, select oAuth2 \> Sign In.

	When prompted, enter your Office365Mon admin credentials and follow the SQL Sentry authentication process.

	![](media/powerbi-content-pack-office365mon/creds.png)
    
    ![](media/powerbi-content-pack-office365mon/creds2.png)

6.  After Power BI imports the data you will see a new dashboard, report, and dataset in the left navigation pane. New items are marked with a yellow asterisk \*, select the Office365Mon entry.

	![](media/powerbi-content-pack-office365mon/dashboard4.png)



What can you do now?

-   Try asking a question in the Q&A box at the top of the dashboard, such as "average request time in the last week"

-   Change the tiles in the dashboard.

-   Select a tile to open the underlying report.

-   Rename the dashboard: Select the ellipsis (…) next to the dashboard \> Rename.




## Troubleshooting

If you get a **"login failed"** error after using your Office365Mon subscription credentials to login, then the account you are using doesn't have permissions to retrieve the Office365Mon data from your account. Verify it is an admin account and try again.


See Also:


[Get started with Power BI](powerbi-service-get-started.md)

[Get Data for Power BI](powerbi-service-get-data.md)

