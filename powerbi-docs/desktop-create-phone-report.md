---
title: Create reports optimized for the Power BI phone apps
description: Learn how to optimize report pages in Power BI Desktop for the Power BI phone apps.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
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
ms.date: 12/08/2017
ms.author: maggies

LocalizationGroup: Create reports
---
# Create reports optimized for the Power BI phone apps
When you [create a report in Power BI Desktop](desktop-report-view.md), you can improve the experience of using it in the mobile apps on phones by creating a version of the report specifically for the phone. You adapt your report for the phone by rearranging and resizing visuals, maybe not including all of them, for an optimal experience. Plus you can create [*responsive* visuals](#optimize-a-visual-for-any-size) and [responsive slicers](#enhance-slicers-to-to-work-well-in-phone-reports) that resize well for viewing on a phone. Also, if you add filters to your report, those filters show up automatically in the phone report. Your report readers can see them and filter the report with them.

![Optimized report on a phone](media/desktop-create-phone-report/07-power-bi-phone-report-portrait.png)

## Lay out a report page for the phone in Power BI Desktop
After you [create a report in Power BI Desktop](desktop-report-view.md), you can optimize it for phones.

1. In Power BI Desktop, select **Report View** in the left navigation bar.
   
    ![Report View icon](media/desktop-create-phone-report/pbi_reportviewinpbidesigner_changeview.png)
2. On the **View** tab, select **Phone Layout**.  
   
    ![Phone Layout icon](media/desktop-create-phone-report/power-bi-phone-layout-icon.png)
   
    You see a blank phone canvas. All of the visuals on the original report page are listed in the Visualizations pane on the right.
3. To add a visual to the phone layout, drag it from the Visualizations pane to the phone canvas.
   
    Phone reports use a grid layout. As you drag visuals to the mobile canvas, they snap to that grid.
   
    ![Drag and drop a visual](media/desktop-create-phone-report/02_dragging_and_droping_a_vis.gif)
   
    You can add some or all the master report page visuals to the phone report page. You can add each visual only once.
4. You can resize your visuals on the grid, as you would for tiles on dashboards and mobile dashboards.
   
   > [!NOTE]
   > The phone report grid scales across phones of different sizes, so your report will look as good on small- and on large-screen phones.
   > 
   > 
   
   ![Resize a visual](media/desktop-create-phone-report/03_resizing_a_viz_to_grid.gif)

## Optimize a visual for any size
You can set the visuals in your dashboard or report to be *responsive*, to change dynamically to display the maximum amount of data and insight, no matter the screen size. 

As a visual changes size, Power BI prioritizes the data view, for example removing padding and moving the legend to the top of the visual automatically, so the visual remains informative even as it gets smaller.

![Responsive visual resizing](media/desktop-create-phone-report/power-bi-responsive-visual.gif)

You choose whether to turn on responsiveness for each visual. Read more about [optimizing visuals](desktop-create-responsive-visuals.md).

## Considerations when creating phone report layouts
* For reports with multiple pages, you can optimize all the pages or only a few. 
* If you've defined a background color for a report page, the phone report will have the same background color.
* You can’t modify formatting settings for just the phone. Formatting is consistent between master and mobile layouts. For example, font sizes will be the same.
* To change a visual, such as changing its formatting, dataset, filters, or any other attribute, return to the regular report authoring mode.
* Power BI provides default titles and page names for phone reports in the mobile app. If you’ve created text visuals for titles and page names in your report, consider not adding them to your phone reports.     

## Remove a visual from the phone layout
* To remove a visual, click the X in the top-right  of the visual on the phone canvas, or select it and press **Delete**.
  
   Removing the visual here only removes it from the phone layout canvas. The visual and the original report aren't affected.
  
   ![Removing a visual](media/desktop-create-phone-report/05_removing_a_vis.gif)

## Enhance slicers to to work well in phone reports
Slicers offer on-canvas filtering of report data. When designing slicers in the regular report authoring mode, you can modify some slicer settings to make them more usable in phone reports:

* Decide if report readers can select only one or more than one item.
* Put a box around the slicer to make the report easier to scan.
* Make the slicer vertical, horizontal, or *responsive*. 

If you make the slicer responsive, as you change its size and shape it shows more or fewer options. It can be tall, short, wide, or narrow. If you make it small enough, it becomes just a filter icon on the report page. 

![Power BI responsive slicer](media/desktop-create-phone-report/power-bi-slicer-2-rows.png)

Read more about [creating responsive slicers](power-bi-slicer-filter-responsive.md).

## Publish a phone report
* To publish the phone version of a report, you [publish the main report from Power BI Desktop to the Power BI service](desktop-upload-desktop-files.md), and the phone version publishes at the same time.
  
    Read more about [sharing and permissions in Power BI](service-how-to-collaborate-distribute-dashboards-reports.md).

## View optimized and unoptimized reports on a phone
In the mobile apps on phones, Power BI automatically detects optimized and unoptimized phone reports. If a phone-optimized report exists, the Power BI phone app automatically opens the report in phone report mode.

If a phone-optimized report doesn’t exist, the report opens in the unoptimized, landscape view.  

When in a phone report, changing the phone’s orientation to landscape will open the report in the unoptimized view with the original report layout, whether the report is optimized or not.

If you only optimize some pages, readers will see a message in portrait view, indicating the report is available in landscape.

![Phone page not optimized](media/desktop-create-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Report readers can turn their phones sideways to see the page in landscape mode. Read more about [interacting with Power BI reports optimized for your phone](mobile-apps-view-phone-report.md).

## Next steps
* [Create a phone view of a dashboard in Power BI](service-create-dashboard-mobile-phone-view.md)
* [View Power BI reports optimized for your phone](mobile-apps-view-phone-report.md)
* [Create responsive visuals optimized for any size](desktop-create-responsive-visuals.md)
* More questions? [Try asking the Power BI Community](http://community.powerbi.com/)

