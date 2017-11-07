---
title: Hyperlinks in tables
description: Hyperlinks in tables
services: powerbi
documentationcenter: ''
author: mihart
manager: erikre
backup: ''
editor: ''
tags: ''
qualityfocus: identified
qualitydate: ''

ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart

---
# Hyperlinks in tables
This topic teaches you how to use Power BI Desktop to create hyperlinks. Once created, use either Desktop or Power BI service to add those hyperlinks to your report tables and matrixes. 

![](media/powerbi-service-hyperlinks-in-tables/hyperlinkedTable.png)

> **NOTE**:
> Hyperlinks in [tiles on dashboards](powerbi-service-edit-a-tile-in-a-dashboard.md) and [text boxes on dashboards](powerbi-service-add-a-widget-to-a-dashboard.md) can be created on-the-fly using Power BI service. Hyperlinks in [text boxes in reports](powerbi-service-add-a-hyperlink-to-a-text-box.md) can be created on-the-fly using Power BI service and Power BI Desktop.
> 
> 

## To create a hyperlink in a table or matrix using Power BI Desktop
Hyperlinks in tables and matrixes can be created in Power BI Desktop, but not from Power BI Service. Hyperlinks can also be created in Excel Power Pivot before the workbook is imported into Power BI. Both methods are described below.

## Create a table or matrix hyperlink in Power BI Desktop
The procedure for adding a hyperlink depends on whether you've imported the data or connected to it using DirectQuery. Both scenarios are described below.

### For data imported into Power BI
1. If the hyperlink doesn't already exist as a field in your dataset, use Desktop to add it as a [custom column](powerbi-desktop-common-query-tasks.md).
2. In Data view, select the column and in the **Modeling** tab choose the dropdown for **Data Category**.
   
    ![](media/powerbi-service-hyperlinks-in-tables/PBI_data_category.png)
3. Select **Web URL**.
4. Switch to Report view and create a table or matrix using the field categorized as a Web URL. The hyperlinks will be blue and underlined.
   
    ![](media/powerbi-service-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)
5. If you don't want to display a long URL in a table, you can display a hyperlink icon  ![](media/powerbi-service-hyperlinks-in-tables/power-bi-hyperlink-icon.png) instead. Note that you can't display icons in matrixes.
   
   * Select the chart to make it active.
   * Select the paint roller icon ![](media/powerbi-service-hyperlinks-in-tables/power-bi-paintroller.png) to open the Formatting tab.
   * Expand **Values**, locate **URL icon** and turn it to **On.**
6. (Optional) [Publish the report from Desktop to Power BI service](guided-learning/publishingandsharing.yml#step-2) and open the report in Power BI service. The hyperlinks will work there as well.

### For data connected with DirectQuery
You won't be able to create a new column in DirectQuery mode.  But if your data already contains URLs, you can turn those into hyperlinks.

1. In Report view, create a table using a field that contains URLs.
2. Select the column, and in the **Modeling** tab, choose the dropdown for **Data Category**.
3. Select **Web URL**. The hyperlinks will be blue and underlined.
4. (Optional) [Publish the report from Desktop to Power BI service](guided-learning/publishingandsharing.yml#step-2) and open the report in Power BI service. The hyperlinks will work there as well.

## Create a table or matrix hyperlink in Excel Power Pivot
Another way to add hyperlinks to your Power BI tables and matrixes is to create the hyperlinks in the dataset before you import/connect to that dataset from Power BI. This example uses an Excel workbook.

1. Open the workbook in Excel.
2. Select the **PowerPivot** tab and then choose **Manage**.
   
   ![](media/powerbi-service-hyperlinks-in-tables/createHyperlinkInPowerPivot2.png)
3. When PowerPivot opens, select the **Advanced** tab.
   
   ![](media/powerbi-service-hyperlinks-in-tables/createHyperlinkInPowerPivot3.png)
4. Place your cursor in the column that contains the URLs that you'd like to turn into hyperlinks in Power BI tables.
   
   > **NOTE**: The URLS must start with **http:// , https://** or **www**.
   > 
   > 
5. In the **Reporting Properties** group, select the **Data Category** dropdown and choose **Web URL**. 
   
   ![](media/powerbi-service-hyperlinks-in-tables/createHyperlinksNew.png)
6. From the Power BI service or Power BI Desktop, connect to or import this workbook.
7. Create a table visualization that includes the URL field.
   
   ![](media/powerbi-service-hyperlinks-in-tables/hyperlinksInTables.gif)

## See also
[Visualizations in Power BI reports](powerbi-service-visualizations-for-reports.md)

[Power BI - Basic Concepts](powerbi-service-basic-concepts.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/)

