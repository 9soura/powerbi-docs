﻿<properties
   pageTitle="Tutorial: Get started with Power BI Q&A"
   description="Tutorial: get started with Power BI Q&A with the Retail Analysis sample"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="07/05/2016"
   ms.author="mihart"/>
# Tutorial: use Power BI Q&A with the Retail Analysis sample

Sometimes the fastest way to get an answer from your data is to ask a question using natural language.  In this tutorial we'll look at 2 different ways of creating the same visualization: building it in a report and asking a question with Q&A.  


1. From your Power BI workspace, select **Get Data** \> **Samples** \> **Retail Analysis Sample** > **Connect**.

	![](media/powerbi-service-tutorial-introduction-to-q-and-a/gnaTutorial_1.png)

2. The dashboard contains an area chart tile for "Last Year Sales and This Year Sales."  Select this tile. 

	-   If this tile was created with Q&A, selecting the tile will open Q&A. 

	-   But this tile was created in a report, so the report opens to the page that contains this visualization.

3. Open the report in Editing View by selecting **Edit Report**.

	![](media/powerbi-service-tutorial-introduction-to-q-and-a/gnaTutorial_2.png)

4. Select the area chart and review the settings in the **Fields** pane.  The report creator built this chart by selecting these 3 values (**Time > FiscalMonth**, **Sales > This Year Sales**, **Sales >Last Year Sales >Value**) and organizing them in the **Axis** and **Values** wells.

	![](media/powerbi-service-tutorial-introduction-to-q-and-a/gnaTutorial_3.png)

How would we go about creating this same line chart using Q&A?

1.  Navigate back to your the Retail Analysis Sample dashboard.

2.  Using natural language, type something like this into the question box:

    **what were this year sales and last year sales by month as area chart**

    As you type your question, Q&A picks the best visualization to display your answer; and the visualization changes dynamically as you modify the question. Also, Q&A helps you format your question with suggestions, auto-complete, and spelling corrections.

    When you finish typing your question, the result is the exact same chart that we saw in the report.  But creating it this way was much faster!

    ![](media/powerbi-service-tutorial-introduction-to-q-and-a/powerbi-qna-areachart.png)

4. Similar to working with reports, within Q&A you have access to the Visualizations, Filters and Fields panes.  Open these panes to further explore and modify your visual.

3.  To pin the chart to your dashboard, select the pin icon ![](media/powerbi-service-tutorial-introduction-to-q-and-a/pinNoOutline.png).

## See also

[What type of questions can I ask Q&A?](powerbi-service-q-and-a.md)

[Q&A in Power BI](powerbi-service-q-and-a.md)

[Make your data work well with Q&A in Power BI](powerbi-service-make-your-data-work-well-with-q-and-a.md)

[preparing a workbook for Q&A](powerbi-service-make-your-data-work-well-with-q-and-a.md)
