<properties
   pageTitle="Tutorial: Power BI integration with Microsoft Flow"
   description="Learn how to create Flows triggered by Power BI data alerts."
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="11/21/2016"
   ms.author="mihart"/>

# Microsoft Flow and Power BI
##  What is Microsoft Flow
[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started) is a SaaS offering for automating workflows across the growing number of applications and SaaS services that business users rely on. With Flow you can automate tasks by integrating your favorite apps and services to get notifications, synchronize files, collect data, and more. Repetitive tasks become easy with workflow automation.

[Get started using Flow now.](flow.microsoft.com/documentation/getting-started)

![](media/powerbi-service-flow-integration/power-bi-flow.png)

##  Create a flow 
This tutorial will show you how to create two different flows; one from a template and one from scratch. To follow along, [create a data alert in Power BI](powerbi-service-set-data-alerts.md) and [sign up for Microsoft Flow](https://flow.microsoft.com/en-us/#home-signup) (it's free!).

##  Create a flow that uses Power BI - from a template
In this task we'll use a template to create a simple flow that is triggered by a Power BI data alert (notification).

1.  Sign in to Microsoft Flow.

2.  Select **My flows**.

    ![](media/powerbi-service-flow-integration/power-bi-my-flows.png)

3. Select **Create from template**.

    ![](media/powerbi-service-flow-integration/power-bi-template.png)

4. Use the Search box to find Power BI templates and select **Post a message to a Slack channel when a Power BI data alert is triggered**.

    ![](media/powerbi-service-flow-integration/power-bi-template2.png)

5.  Select **Use this template**.

    ![](media/powerbi-service-flow-integration/power-bi-use-template.png)

6.  If prompted, connect to Slack and Power BI by selecting **Sign in** and then following the prompts. A green checkmark lets you know that you're signed in.  After you confirm your conections, select **Continue**.

    ![](media/powerbi-service-flow-integration/power-bi-flow-signin.png)

### Build the flow

This template has one trigger (Power BI data alert for new Olympic medals for Ireland) and one action (post a message to Slack). As you select a field, Flow displays dynamic content that you can include.  In this example we've included the tile value and the tile URL in the message body. 

![](media/powerbi-service-flow-integration/power-bi-flow-template.png)

1.  From the trigger dropdown, select a Power BI data alert. 

    ![](media/powerbi-service-flow-integration/power-bi-trigger-flow.png)

2.  To post to Slack, enter a channel name and message text. 

    ![](media/powerbi-service-flow-integration/power-bi-flow-slacker.png) 

3.  When you're done, select **Create flow**.  The flow is created and evaluated.  Flow lets you know if it finds errors. 

4.  If errors are found, select **Edit flow** to fix them, otherwise, select **Done** to run the new flow. 

    ![](media/powerbi-service-flow-integration/power-bi-flow-running.png) 

5.  Open your slack account to see the message.  

    ![](media/powerbi-service-flow-integration/power-bi-slack-message.png) 

##  Create a Flow that uses Power BI - from blank
In this task we'll create a simple flow from scratch that is triggered by a Power BI data alert (notification).

1.  Sign in to Microsoft Flow.

2.  Select **My flows** > **Create from scratch (blank)**.

    ![](media/powerbi-service-flow-integration/power-bi-my-flows.png)

3. Use the Search box to find a Power BI trigger and select **Power BI - When a data driver alert is triggered**.

### Build your flow

1. From the dropdown, select the name of your alert.  To learn how to create an alert, see [Data alerts in Power BI](powerbi-service-set-data-alerts.md).

    ![](media/powerbi-service-flow-integration/power-bi-totalstores.png) 

2.  Select **New step** > **Add an action**.

    ![](media/powerbi-service-flow-integration/power-bi-new-step.png) 

3.  Search for **Outlook** and select **Create event**.

    ![](media/powerbi-service-flow-integration/power-bi-flow-create-event.png) 

4.  Fill in the event fields. As you select a field, Flow displays dynamic content that you can include.

    ![](media/powerbi-service-flow-integration/power-bi-flow-event.png) 

5.  Selet **Create flow** when done.  Flow saves and evaluates the flow. If there are no errors, select **Done** to run this flow.  The new flow is added to your **My flows** page.

    ![](media/powerbi-service-flow-integration/power-bi-flow-running.png) 

7. When the flow is triggered by your Power BI data alert, you'll receive an Outlook event notification similar to this one.

    ![](media/powerbi-service-flow-integration/power-bi-flow-notice.png) 



### See also
- [Get started with Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started/)
-   [Set data alerts in Power BI service](powerbi-service-set-data-alerts.md)
- [Set data alerts on your iphone](powerbi-mobile-set-data-alerts-in-the-iphone-app.md)
- [Set data alerts in the Power BI mobile app for Windows 10]
-   More questions? [Try the Power BI Community](http://community.powerbi.com/)
