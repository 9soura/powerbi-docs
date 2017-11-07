---
title: Pin a tile to a Power BI dashboard from Q&A
description: Documentation on how to pin a tile to a Power BI dashboard from the Q&A question box
services: powerbi
documentationcenter: ''
author: mihart
manager: erikre
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''

ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/09/2017
ms.author: mihart

---
# Pin a tile to a dashboard from Q&A
## How to pin a tile from Q&A
Q&A is the Power BI ad hoc reporting tool. Need to find a particular insight? Ask a question about your data, and receive an answer in the form of a visualization.

> **NOTE**: To follow along, open the [Retail Analysis sample](sample-retail-analysis.md).
> 
> 

1. Open a [dashboard](powerbi-service-dashboards.md) that has at least one tile pinned from a report. When you ask a question, Power BI looks for the answer in any dataset that has a tile pinned to that dashboard.  To learn more, see [get data](service-get-data.md).
2. In the question box at the top of your dashboard, start typing what you want to know about your data.  
   ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-the-question-box/power-bi-question-box.png)
3. For example, as you type "last year sales by month and territory"...  
   ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-the-question-box/power-bi-type-q-and-a.png)
   
   the question box gives you suggestions.
4. To add the chart to your dashboard as a tile, select the pin ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-the-question-box/PBI_PinTile.png) on the top-right side of the canvas.
5. Pin the tile to an existing dashboard or to a new dashboard. 
   
   * Existing dashboard: select the name of the dashboard from the dropdown. Your choices will be limited to only those dashboards withing the current workspace.
   * New dashboard: type the name of the new dashboard and it will be added to your current workspace.
6. Select **Pin**.
   
   A success message (near the top-right corner) lets you know the visualization was added, as a tile, to your dashboard.  
   
   ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-the-question-box/power-bi-pin.png)
7. Select **Go to dashboard** to see the new tile. There, you can [rename, resize, add a hyperlink, and reposition the tile, and more](powerbi-service-edit-a-tile-in-a-dashboard.md) on your dashboard. 
   
   ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-the-question-box/power-bi-pinned.png)

## Considerations and troubleshooting
* When you start typing a question, Q&A immediately begins searching for the best answer from all datasets associated with the current dashboard.  The "current dashboard" is the dashboard listed in the top navigation bar. For example, this question is being asked in the **Retail Analysis Sample** dashboard that is part of the **mihart** app workspace.
  
  ![](media/powerbi-service-pin-a-tile-to-a-dashboard-from-the-question-box/power-bi-navbar.png)
* **How does Q&A know which datasets to use**?  Q&A has access to all datasets that have visualizations pinned to that dashboard.

## Next steps
[Rename, resize, add a hyperlink, reposition the tile, and more](powerbi-service-edit-a-tile-in-a-dashboard.md)    
[Display your dashboard tile in Focus mode](powerbi-service-display-dash-in-focus-mode.md)     
[Back to Q&A in Power BI](powerbi-service-q-and-a.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)

