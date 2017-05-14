﻿<properties
   pageTitle="Reports in Power BI"
   description="Reports in Power BI"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="erikre"
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
   ms.date="05/12/2017"
   ms.author="mihart"/>
# Reports in Power BI

##  What is a Power BI report?

A Power BI ***report*** is a multi-perspective view into a dataset, with visualizations that represent different findings and insights from that dataset.  A report can have a single visualization or pages full of visualizations. Depending on your job role, you may be someone who *creates* reports and/or you may be someone who *consumes* or uses reports.

![](media/powerbi-service-reports/reportview.png)

This report has 3 pages (or tabs) and we're currently viewing the Store Sales Overview page. On this page are 6 different visualizations and a page title. Visualizations can be *pinned* to dashboards and when that pinned visualization is selected, it opens the report it was pinned from.

If you're new to Power BI, you can get a good foundation by reading [Power BI basic concepts](powerbi-service-basic-concepts.md)

>**NOTE**: Reports are a feature of Power BI service and Power BI Desktop. The experience of working with reports is almost identical. However, for mobile, you can't create reports but you can [view, share, and annotate reports](powerbi-mobile-reports-in-the-iphone-app.md).

##    Advantages of reports

Reports are based on a single dataset. The visualizations in a report each represent a nugget of information. And the visualizations aren't static; you can add and remove data, change visualization types, and apply filters and slicers as you dig into the data to discover insights and look for answers. Like a dashboard, but more-so, a report is highly interactive and highly customizable and the visualizations update as the underlying data changes.

##    Dashboards versus reports

[Dashboards](powerbi-service-dashboards.md) are often confused with reports since they too are canvases filled with visualizations. But there are some major differences.  


|**Capability**  |**Dashboards**  |**Reports**  |
|---------|---------|---------|
|Pages       |  One page       | One or more pages        |
|Data sources     | One or more reports and one or more datasets per dashboard       | A single dataset per report       |
|Available in Power BI Desktop  | No  | Yes, can create and view reports in Desktop  |
|Pinning   | Can pin existing visualizations (tiles) only from current dashboard to your other dashboards  | Can pin visualizations (as tiles) to any of your dashboards. Can pin entire report pages to any of your dashboards.|
|Subscribe    | Can't subscribe to a dashboard        | Can subscribe to report pages        |
|Filtering     | Can't filter or slice       | Many different ways to filter, highlight, and slice        |
|Set alerts     | Can create alerts to email you when certain conditions are met     |  No       |
|Feature    | Can set one dashboard as your "featured" dashboard        | Cannot create a featured report        |
|Natural language queries     | Available from dashboard        | Not available from reports        |
|Can change visualization type     | No. In fact, if a report owner changes the visualization type in the report, the pinned visualization on the dashboard does not update        | Yes        |
|Can see underlying dataset tables and fields | No. Can export data but can't see tables and fields in the dashboard itself.        | Yes. Can see dataset tables and fields and values.
|Can create visualizations  | Limited to adding widgets to dashboard using "Add tile"   | Can create many different types of visuals, add custom visuals, edit visuals and more with Editing permissions   |
|Customization  | Can do things with the visualizations (tiles) like move and arrange, resize, add links, rename, delete, and display full screen. But the data and visualizations themselves are read-only. | In Reading view you can publish, embed, filter,export, download as .pbix, view related content, generate QR codes, analyze in Excel, and more.  In Editing view you can do everything mentioned so far and so much more.



##  Report ***creators*** and report ***consumers***  
Depending on your role, you may be someone who creates reports for your own use or to share with colleagues. You want to learn how to create and share reports. Or, you may be someone who receives reports from others. You want to learn how to understand and interact with the reports.

Here are some topics, by role, to help you get started.

###    If you will be creating and sharing reports
- Start with a [tour of Power BI service](powerbi-service-take-a-tour.md) so you know where to find reports and report tools.
- Take a tour of the [report editor](powerbi-service-the-report-editor-take-a-tour.md).
-  Learn how to [create a report from a dataset](powerbi-service-create-a-new-report.md).
- [Learn how to use visualization, page, and report-level filters](powerbi-service-how-to-use-a-report-filter.md)
- Discover all the different ways you can [share a report with colleagues](powerbi-service-share-unshare-dashboard.md).

###    If you will be receiving and consuming reports
- Start with a [tour of Power BI service](powerbi-service-take-a-tour.md) so you know where to find reports and report tools.
-  Learn how to [open a report](powerbi-service-open-a-report-in-reading-view.md) and all the interaction available in [Reading view](powerbi-service-dashboard-tiles.md).
- Get comfortable with reports by taking a tour of one of our [samples](powerbi-sample-tutorial-connect-to-the-samples.md).  
-  Don't need the report any more? You can [remove it](powerbi-service-delete-a-report.md).
- To see which dataset the report is using and which dashboards have tiles pinned from the report, [view related content](powerbi-service-related-content.md).


>[AZURE.TIP]If you didn’t find what you’re looking for here, use the Table of Contents to the left to browse all *report* topics.



## See Also

[Get Started with Power BI](powerbi-service-get-started.md) 

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)
