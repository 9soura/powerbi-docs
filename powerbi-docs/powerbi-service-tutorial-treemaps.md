---
title: Treemaps in Power BI (Tutorial)
description: 'Tutorial: Treemaps in Power BI'
services: powerbi
documentationcenter: ''
author: mihart
manager: erikre
backup: ''
editor: ''
tags: ''
featuredvideoid: IkJda4O7oGs
qualityfocus: no
qualitydate: ''

ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart

---
# Treemaps in Power BI (Tutorial)
Treemaps display hierarchical data as a set of nested rectangles.  Each level of the hierarchy is represented by a colored rectangle (often called a "branch") containing other rectangles ("leaves").  The space inside each rectangle is allocated based on the quantitative value being measured, with the rectangles arranged in size from top left (largest) to bottom right (smallest).

![](media/powerbi-service-tutorial-treemaps/pbi-Nancy_viz_treemap.png)

For example, if I'm analyzing my sales, I might have top-level rectangles (branches) for the clothing categories: **Urban**, **Rural**, **Youth**, and **Mix**.  My category rectangles would contain smaller rectangles (leaves) for the clothing manufacturers within that category, and these smaller rectangles would be sized and shaded based on the number sold.  In the **Urban** branch above, lots of Maximus clothing was sold, less Natura and Fama, and very little Leo.  So, the **Urban** branch of my Treemap would have the largest rectangle for Maximus (in the top left corner), slightly-smaller rectangles for Natura and Fama, lots of other rectangles representing all the other clothing sold, and a tiny rectangle for Leo.  And I could compare the number of items sold across the other clothing categories by comparing the size and shading of each leaf node; the larger the rectangle and the darker the shading, the higher the value.

## When to use a treemap
Treemaps are a great choice:

* to display large amounts of hierarchical data.
* when a bar chart can't effectively handle the large number of values.
* to show the proportions between each part and the whole.
* to show the pattern of the distribution of the measure across each level of categories in the hierarchy.
* to show attributes using size and color coding.
* to spot patterns, outliers, most-important contributors, and exceptions.

## Create a basic treemap
Want to watch someone else create a treemap first?  Skip to 2:10 in this video to watch Amanda create a treemap.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

Or, create your own treemap. These instructions use the Retail Analysis Sample. To follow along,  [download the sample](powerbi-sample-datasets.md), sign in to Power BI and select **Get Data \> Excel Workbook \>  Connect \> Retail Analysis Sample**.**xlsx**.

1. Start in [Editing View](powerbi-service-interact-with-a-report-in-editing-view.md) and select the **Sales** > **Last Years Sales** measure.   
   ![](media/powerbi-service-tutorial-treemaps/treemapFirstValue_new.png)
2. Convert the chart to a treemap.  
   ![](media/powerbi-service-tutorial-treemaps/treemapConvertTo_new.png)
3. Drag **Item** > **Category** to the **Group** well. Power BI creates a treemap where the size of the rectangles reflect total sales and the color represents the category.  In essence you've created a hierarchy that visually describes the relative size of total sales by category.  The **Mens** category has the highest sales and the **Hosiery** category has the lowest.
   ![](media/powerbi-service-tutorial-treemaps/treemapComplete_new.png)
4. Drag **Store** > **Chain** to the **Details** well to complete your treemap. You can now compare last year's sales by category and chain.   
   ![](media/powerbi-service-tutorial-treemaps/treemap_addGroup_new.png)
   
   > [!NOTE]
   > Color Saturation and Details cannot be used at the same time.
   > 
   > 
5. Hover over a **Chain** area to reveal the tooltip for that portion of the **Category**.  For example, hovering over **Lindseys** in the **040-Juniors** rectangle reveals the tooltip for Lindsey's portion of the Juniors category.  
   ![](media/powerbi-service-tutorial-treemaps/treemapHoverDetail_new.png)
6. [Add the treemap as a dashboard tile (pin the visual)](powerbi-service-dashboard-tiles.md). 
7. [Save the report](powerbi-service-save-a-report.md).

## Highlighting and cross-filtering
For information about using the Filters pane, see [Add a filter to a report](powerbi-service-add-a-filter-to-a-report.md).

Highlighting a Category or Details in a treemap cross-highlights and cross-filters the other visualizations on the report page... and vice versa. To follow along, either add some visuals to the same page or copy/paste the treemap to a report page that already has other visuals.

1. On the treemap, select either a Category or a Chain within a Category.  This cross-highlights the other visualizations on the page. Selecting **050-Shoes**, for example, shows me that last year's sales for shoes was $3,640,471 with $2,174,185 of that coming from Fashions Direct.  
   ![](media/powerbi-service-tutorial-treemaps/treemapHiliting.png)
2. In the **Last Year Sales by Chain** pie chart, select the **Fashions Direct** slice.  
   ![](media/powerbi-service-tutorial-treemaps/treemapNoOwl.gif)
3. To manage how charts cross-highlight and cross-filter each other, see [Visualization interactions in a Power BI report](powerbi-service-visual-interactions.md)

## See also
[Reports in Power BI](powerbi-service-reports.md)  
[Add a visualization to a report](powerbi-service-add-visualizations-to-a-report-i.md)  
[Visualization types in Power BI](powerbi-service-visualization-types-for-reports-and-q-and-a.md)
[ Pin a visualization to a dashboard](powerbi-service-pin-a-tile-to-a-dashboard-from-a-report.md)  
[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)  
[Try it out -- it's free!](https://powerbi.com/)

More questions? [Try the Power BI Community](http://community.powerbi.com/)  

