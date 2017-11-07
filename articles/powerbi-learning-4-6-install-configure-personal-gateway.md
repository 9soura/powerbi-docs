---
title: Install and configure a Personal Gateway
description: Use a Personal Gateway to automatically update on-premises data
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: erikre
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
featuredvideoid: xjcO5tNvjGs
featuredvideothumb: ''
courseduration: 11m

ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi

---
# Install and Configure a Personal Gateway
In previous topics we've looked at how you can use Power BI to connect to data sources, and how to manually refresh your datasets on the Power BI service. However, you're not going to want to manually refresh things every time your data changes, so you can use Power BI to set up a scheduled refresh that will connect to your data sources and publish them into the Power BI Service automatically. This also gives you a way to connect the service with any on-premises data sources, including Excel files, Access databases, SQL databases, and more.

The system that lets you connect your on-premises data sources to the Power BI service is called the **Data Gateway**. It's a small application that runs on your computer, and uses a pre-arranged schedule to connect to your data, gather any updates, and push them up to the Power BI service. The **Personal Gateway** is a version of the **Data Gateway** that can be used without any administrator configuration.

> Note: The computer  that is running the Power BI Personal Gateway *must* be on and connected to the Internet for **Personal Gateway** to work properly.
> 
> 

To set up your **Personal Gateway**, first login to the Power BI service. Select the **Download** icon in the top right-hand corner of the screen, and then select **Data Gateways** from the menu.

![](media/powerbi-learning-4-6-install-configure-personal-gateway/4-6_1b.png)

From there you'll be taken to a web page where you can select the **Power BI Gateway - Personal**, as shown below.

![](media/powerbi-learning-4-6-install-configure-personal-gateway/4-6_2b.png)

Run the application once it finishes downloading, and complete the installation wizard.

![](media/powerbi-learning-4-6-install-configure-personal-gateway/4-6_3a.png)

You'll then be prompted to launch the configuration wizard to set up your gateway.

![](media/powerbi-learning-4-6-install-configure-personal-gateway/4-6_3b.png)

You'll be asked first to login to your Power BI service account, and then to login to the machine's Windows account, since the Gateway service runs under your account.

![](media/powerbi-learning-4-6-install-configure-personal-gateway/4-6_3c.png)

Return to the Power BI service. Select the ellipsis (three dots) menu next to the dataset you want to refresh, and then select **Schedule Refresh**. This opens the **Refresh Settings** page. Power BI detects that you've installed a **Personal Gateway**, and lets you know its status.

Select **Edit credentials** next to each applicable data source and set up authentication.

![](media/powerbi-learning-4-6-install-configure-personal-gateway/4-6_6.png)

Finally, set the options under **Schedule Refresh** to activate automatic updates and set when and how frequently they occur.

![](media/powerbi-learning-4-6-install-configure-personal-gateway/4-6_7.png)

And that's it. On the scheduled times, Power BI will go out to those data sources, using the credentials you provided and the connection to the computer that has your **Personal Gateway** running, and update the reports and datasets according to your schedule. The next time you go to Power BI, those dashboards, reports, and datasets will reflect data as of the most recent scheduled refresh.

## What's Next
**Congratulations!** You've completed this **Exploring Data** section of the **Guided Learning** course for Power BI. The Power BI service is full of interesting ways to explore data, share insights, and interact with visuals. And it's all accessible from a browser, from a service that you can connect to wherever you are.

One powerful and well-known partner of Power BI is **Excel**. Power BI and Excel are designed to work well together; your workbooks will feel at home in Power BI, and it's easy to get them there.

![](media/powerbi-learning-4-6-install-configure-personal-gateway/5-1_1.png)

How easy? In the next section, **Power BI and Excel** you learn exactly that.

See you in the next section!

