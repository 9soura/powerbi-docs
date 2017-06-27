﻿<properties
   pageTitle="Table visualizations in reports and dashboards (Tutorial)"
   description="Tips for working with table visualizations in Power BI reports and dashboards, including how to resize column widths."
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="erikre"
   backup=""
   editor=""
   tags=""
   featuredVideoId=""
      qualityFocus=""
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="06/28/2017"
   ms.author="mihart"/>

# Working with tables in Power BI reports and dashboards (Tutorial)

A table is a grid that contains related data in a logical series of rows and columns. It may also contain headers and a row for totals. Tables work well with quantitative comparisons where you are looking at many values for a single category. For example, this table displays 5 different measures for **Category**.

![](media/powerbi-service-tutorial-tables/table.png)

##  When to use a table
Tables are a great choice:

-  to see and compare detailed data and exact values (instead of visual representations)

-  to display data in a tabular format

-   to display numerical data by categories   

>[AZURE.NOTE] If a table has too many values, consider converting it to a matrix and/or using drilldown.

##  Create a table  

To follow along, sign in to Power BI and select **Get Data > Samples > Retail Analysis Sample**. We'll create the table pictured above to display sales values by item category.

1. In **My workspace**, select the Datasets tab, and scroll down to the Retail Analysis Sample dataset you just added.  Select the **Create report** icon.

   ![](media/powerbi-service-tutorial-tables/power-bi-create-report.png)

2. In the report editor, select **Item** > **Category**.  Power BI automatically creates a table that lists all the categories.

    ![](media/powerbi-service-tutorial-tables/power-bi-table1.png)

2.  Select **Sales > Average Unit Price** and **Sales > Last Year Sales** and **Sales > This Year Sales** and choose all 3 options (Value, Goal, Status).   

3. In the Visualizations pane, locate the **Values** well and drag-and-drop the values until the order of your chart columns matches the first image on this page.  Your Values well should look like this.

    ![](media/powerbi-service-tutorial-tables/power-bi-table2.png)

4. Pin the table to the dashboard by selecting the pin icon  

     ![](media/powerbi-service-tutorial-tables/PBI_PinTile.png)

## Format the table
There are many many ways to format a table and we'll only cover a few of them here. A great way to learn about the other formatting options is to open the Formatting pane (Paint roller icon) and explore.

###    Conditional formatting
One type of formatting is referred to as *conditional formatting* and is applied to fields in the **Values** well of the **Visualizations** pane in Power BI service or Desktop. 

With conditional formatting for tables, you can specify customized cell background colors based on cell values, including using gradient colors. 

1. In the **Visualizations** pane in Power BI service or Desktop, select the down-arrow beside the value in the **Values** well that you want to format (or right-click the field). You can only manage conditional formatting for fields in the **Values** area of the **Fields** well.

    ![](media/powerbi-service-tutorial-tables/power-bi-conditional-formatting-options.png)

2. Select **Color scales**. In the dialog that appears, you can configure the color, as well as the *Minimum* and *Maximum* values. If you select the **Diverging** box, you can configure an optional *Center* value as well.

    ![](media/powerbi-service-tutorial-tables/power-bi-color-scales.png)

    Let's apply some custom formatting to our Average Unit Price values. Select **Diverging**, add some colors, and choose **OK**. 

    ![](media/powerbi-service-tutorial-tables/power-bi-color-scales2.png)

3. Add a new field to the table that has both positive and negative values.  Select **Sales > Total Sales Variance**. 

   ![](media/powerbi-service-tutorial-tables/power-bi-conditional-formatting2.png)

4. Add data bar conditional formatting by selecting the down-arrow beside **Total Sales Variance** and choosing **Conditional formatting > Data bars**.

   ![](media/powerbi-service-tutorial-tables/power-bi-conditional-formatting-data-bars.png)

5. In the dialog that appears, set colors for **Positive bar**, **Negative bar**, place a checkmark next to **Show bar only**, and make any other changes you'd like.
    
    ![](media/powerbi-service-tutorial-tables/power-bi-data-bars.png)

    When you select **OK**, data bars replace the numerical values in the table making it easier to scan.

    ![](media/powerbi-service-tutorial-tables/power-bi-conditional-formatting-data-bars2.png)

6. To remove conditional formatting from a visualization, just right-click the field again, and select **Remove Conditional Formatting**.

>[AZURE.TIP] Conditional formatting is also available from the Formatting pane (paintroller icon). Select the value to format and then set **Color scales** or **Data bars** to On to apply the default settings or, to customize the settings, select **Advanced controls**.
  

##  Adjust the column width of a table
Sometimes Power BI will truncate a column heading in a report and on a dashboard. To show the entire column name, hover over the space to the right of the heading to reveal the double arrows, select and drag.

![](media/powerbi-service-tutorial-tables/resizetable.gif)


More questions? [Try the Power BI Community](http://community.powerbi.com/)
