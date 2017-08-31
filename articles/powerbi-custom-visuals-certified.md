<properties
   pageTitle="Certify a custom visualization"
   description="Description and process for approving and certifying a custom visualization"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="erikre"
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
   ms.date="08/30/2017"
   ms.author="mihart"/>
# Getting a custom visual *certified*

## What is meant by *certified*?
A *certified custom visual* is one that has met a set of code requirements and has passed strict security tests.  Once a custom visual has been certified, it can be  [exported to PowerPoint](powerbi-service-publish-to-powerpoint.md) and will display in the emails received when a user [subscribes to report pages](powerbi-service-subscribe-to-report.md).

- Are you a Web developer and interested in creating your own visualizations and adding them to the Store? See [Get started with Developer Tools](powerbi-custom-visuals-getting-started-with-developer-tools.md) and visit the [Office store](powerbi-custom-visuals-office-store.md) to learn how.

- Is there an Office store visual that you use regularly? Ask the visual developer to certify the visual with Microsoft.  The developer’s contact information is on the visual’s **Learn more** page and listed as **Provider**.


##  Certification requirements
- Office Store approved    
- Custom visual is written with Versioned API 1.2 or higher    
- Code repository available for review (e.g., Visual Code available to us through GitHub)    
- Uses only public reviewable OSS components    
- Does not access external services or resources    


>**TIP**: We recommend that you use EsLint with default security ruleset, to pre-validate your code before submission.

##    Process for submitting a custom visual for Certification

To submit a custom visual for certification:

1. Send an email to Power BI Custom Visuals Support (pbicvsupport@microsoft.com). In the email, include the following information:    
  - Title: Visual Certification Request    
  - Link to GitHub repository where the visual source code is hosted    
  - Adhere to the requirements (see above)    
  - Pass the code and security review    

2. The Custom Visuals team at Microsoft will notify you when your custom visual is certified and added to the Certified list (below), or rejected with a report of the issues that need to be fixed. It is the developer’s responsibility to maintain an open line of communication with Microsoft and to update their Certified visuals as needed.

##  Removal of Power BI Certified custom visuals
Microsoft, at its discretion, may remove a visual from the Certified list.  


##    List of custom visuals that have been certified

|Link to Office store  | Link to video |
|---------|---------|
|[Association Rules (R visual)](https://store.office.com/association-rules-WA104380815.aspx)  |   |
|[Bullet Chart](https://store.office.com/bullet-chart-WA104380755.aspx)   | |
|[Bullet Chart by OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |   |
|[Card with States by OKViz](https://store.office.com/card-with-states-by-okviz-WA104380967.aspx) |[Video](https://youtu.be/myiX0BmZd8U)  |
|[Chiclet slicer](https://store.office.com/chiclet-slicer-WA104380756.aspx)  |[Video](https://youtu.be/iYOkJ1APueY) |
|[Clustering (R visual)](https://store.office.com/clustering-WA104380861.aspx)|     |
|[Clustering with outliers (R visual)](https://store.office.com/clustering-with-outliers-WA104380889.aspx)|   |
|[Correlation Plot (R visual)](https://store.office.com/correlation-plot-WA104380814.aspx)|  |
|[Decision tree (R visual)](https://store.office.com/decision-tree-chart-WA104380817.aspx)|   |
|[Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx)  | [Video](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)    |
|Fly Wheel - coming soon |   |
|[Forecasting with ARIMA (R visual)](https://store.office.com/forecasting-with-arima-WA104380888.aspx)|   |
|[Funnel plot (R visual)](https://store.office.com/funnel-plot-WA104381066.aspx)|  |
|[Gantt](https://store.office.com/gantt-WA104380765.aspx)  |  |
|[Histogram](https://store.office.com/histogram-chart-WA104380776.aspx)  |  |
|[KPI Indicator](https://store.office.com/kpi-indicator-WA104380832.aspx)   |  |
|[Play Axis Dynamic Slicer](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) |   |
|[Radar chart](https://store.office.com/radar-chart-WA104380771.aspx) |   |
|[Sankey](https://store.office.com/ru-ru/app.aspx?assetid=WA104380777.aspx)  |  |
|[Scroller](https://store.office.com/scroller-WA104381018.aspx) |  |
|[Smart Filter by OKViz](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |   |
|[Spline (R visual)](https://store.office.com/spline-chart-WA104380860.aspx)|   |
|[Tachometer](https://store.office.com/tachometer-WA104380937.aspx?)   | |
|[Table Heat Map](https://store.office.com/table-heatmap-WA104380818.aspx)     |   |
|[Timeline slicer](https://store.office.com/timeline-slicer-WA104380786.aspx)    | [Video](https://youtu.be/ozMtZ4_NZ10)|
|[Time series decomposition (R visual](https://store.office.com/time-series-decomposition-chart-WA104380897.aspx?) | |
|[Tornado chart](https://store.office.com/tornado-chart-WA104380768.aspx) |  |
|[Visio visual preview](https://store.office.com/visio-visual-preview-WA104381132.aspx)    |     |
| [Word Cloud](https://store.office.com/word-cloud-WA104380752.aspx?) |[Video](https://youtu.be/AblTenl9fqo)  |



## Next steps

[Download and use custom visuals from the Office store](powerbi-custom-visuals-office-store.md)  
[Getting started with custom visuals developer tools (Preview)](powerbi-custom-visuals-getting-started-with-developer-tools.md)      
[Microsoft's custom visual playlist on YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Visualizations in Power BI](powerbi-service-visualizations-for-reports.md)  
[Custom Visualizations in Power BI](powerbi-custom-visuals.md)  
[Use custom visualizations in Power BI Desktop](powerbi-custom-visuals-use.md)  
[Publish custom visuals to the Office store](powerbi-developer-office-store.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
