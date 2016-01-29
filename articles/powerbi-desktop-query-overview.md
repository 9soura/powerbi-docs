﻿<properties
   pageTitle="Query overview in Power BI Desktop"
   description="Query overview in Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   editor=""
   tags=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="01/28/2016"
   ms.author="davidi"/>

# Query overview in Power BI Desktop  

Welcome to Power BI Desktop. With Power BI Desktop you can connect to the world of data, create compelling and foundational reports, and share your efforts with others – who can then build on your work, and expand their business intelligence efforts.

Power BI Desktop has three views:

-   **Report** view – where you use queries you create to build compelling visualizations, arranged as you want them to appear, and with multiple pages, that you can share with others

-   **Data** view – see the data in your report in data model format, where you can add measures, create new columns, and manage relationships

-   **Relationships** view – get a graphical representation of the relationships that have been established in your data model, and manage or modify them as needed.

These views are accessed by selecting one of the three icons along the left side of Power BI Desktop. In the following image, Report view is selected, indicated by the yellow band beside the icon.  
![](media/powerbi-desktop-query-overview/QueryOverview_ViewIcons.png)

Power BI Desktop also comes with **Query Editor**, where you can connect to one or many data sources, shape and transform the data to meet your needs, then load that model into Power BI Desktop.

This document provides an overview of the work with data in the **Query Editor**. There's more to learn, of course, so at the end of this document you’ll find links to detailed guidance about supported data types, connecting to data, shaping data, creating relationships, and how to get started.

But first, let’s see get acquainted with **Query Editor**.

## The Query Editor  
To get to Query Editor, select **Edit Queries** from the Home tab of Power BI Desktop.  
![](media/powerbi-desktop-query-overview/QueryOverview_QueryView.png)


With no data connections, the Query Editor appears as a blank pane, ready for data.  
![](media/powerbi-desktop-query-overview/QueryOverview_BlankPane.png)

Once a query is loaded, Query Editor view becomes more interesting. If we connect to the following Web data source, Query Editor loads information about the data, which you can then begin to shape.

[*http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx*](http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

Here’s how Query Editor appears once a data connection is established:

1.  In the ribbon, many buttons are now active to interact with the data in the query

2.  In the left pane, queries are listed and available for selection, viewing, and shaping

3.  In the center pane, data from the selected query is displayed and available for shaping

4.  The **Query Settings** window appears, listing the query’s properties and applied steps  
![](media/powerbi-desktop-query-overview/QueryOverview_WithDataConnection.png)

We’ll look at each of these four areas – the ribbon, the queries pane, the data view, and the Query Settings pane – in the following sections.

## The Query Ribbon  
The ribbon in Query Editor consists of four tabs – **Home**, **Transform**, **Add Column**, and **View**.

The **Home** tab contains the common query tasks, including the first step in any query, which is **Get Data.** The following image shows the **Home** ribbon.  
![](media/powerbi-desktop-query-overview/QueryOverview_Ribbon.png)

To connect to data and begin the query building process, select the **Get Data** button. A menu appears, providing the most common data sources.  
![](media/powerbi-desktop-query-overview/QueryOverview_GetDataMenu.png)

For more information about available data sources, see **Data Sources**. For information about connecting to data, including examples and steps, see **Connect to Data**.

The **Transform** tab provides access to common data transformation tasks, such as adding or removing columns, changing data types, splitting columns, and other data-driven tasks. The following image shows the **Transform** tab.  
![](media/powerbi-desktop-query-overview/QueryOverview_TransformRibbon.png)

For more information about transforming data, including examples, see **Combine and Shape Data**.

The **Add Column** tab provides additional tasks associated with adding a column, formatting column data, and adding custom columns. The following image shows the **Add Column** tab.  
![](media/powerbi-desktop-query-overview/QueryOverview_AddColumnRibbon.png)

The **View** tab on the ribbon is used to toggle whether certain panes or windows are displayed. It’s also used to display the Advanced Editor. The following image shows the **View** tab.  
![](media/powerbi-desktop-query-overview/QueryOverview_ViewRibbon.png)

It’s useful to know that many of the tasks available from the ribbon are also available by right-clicking a column, or other data, in the center pane.

## The Left Pane  
The left pane displays the number of active queries, as well as the name of the query. When you select a query from the left pane, its data is displayed in the center pane, where you can shape and transform the data to meet your needs. The following image shows the left pane with multiple queries.  
![](media/powerbi-desktop-query-overview/QueryOverview_TheLeftPane.png)

## The Center (Data) Pane  
In the center pane, or Data pane, date from the selected query is displayed. This is where much of the work of the Query view is accomplished.

In the following image, the Web data connection established earlier is displayed, the **Overall score** column is selected, and its header is right-clicked to show the available menu items. Notice that many of these right-click menu items are the same as buttons in the ribbon tabs.  
![](media/powerbi-desktop-query-overview/QueryOverview_TheCenterPane.png)

When you select a right-click menu item (or a ribbon button), Query applies the step to the data, and saves it as part of the query itself. The steps are recorded in the **Query Settings** pane in sequential order, as described in the next section.  

## The Query Settings Pane  
The **Query Settings** pane is where all steps associated with a query are displayed. For example, in the following image, the **Applied Steps** section of the **Query Settings** pane reflects the fact that we just changed the type of the **Overall score** column.  
![](media/powerbi-desktop-query-overview/QueryOverview_QuerySettingsPane.png)

As additional shaping steps are applied to the query, they are captured in the **Applied Steps** section.

It’s important to know that the underlying data is *not* changed; rather, Query Editor adjusts and shapes its view of the data, and any interaction with the underlying data occurs based on Query Editor’s shaped and modified view of that data.

In the **Query Settings** pane, you can rename steps, delete steps, or reorder the steps as you see fit. To do so, right-click the step in the **Applied Steps** section, and choose from the menu that appears.  
![](media/powerbi-desktop-query-overview/QueryOverview_QuerySettings_Rename.png)

## The Advanced Editor  
If you want to see the code that Query Editor is creating with each step, or want to create your own shaping code, you can use the **Advanced Editor**. To launch the advanced editor, select **View** from the ribbon, then select **Advanced Editor**. A window appears, showing the existing Query code.  
![](media/powerbi-desktop-query-overview/QueryOverview_AdvancedEditor.png)

You can directly edit the code in the **Advanced Editor** window. To close the window, select the **Done** or **Cancel** button.  

## Saving Your Work  
When your query is where you want it, you can have Query Editor apply the changes to the data model into Power BI Desktop, and close Query Editor. To do that, select **Close & Apply** from Query Editor's **File** menu.  
![](media/powerbi-desktop-query-overview/QueryOverview_CloseNLoad.png)

As progress is made, Power BI Desktop provides a dialog to display its status.  
![](media/powerbi-desktop-query-overview/QueryOverview_Loading.png)

Once you have your query where you want it, or if you just want to make sure your work is saved, Power BI Desktop can save your work in the form of a .pbix file.

To save your work, select **File \> Save** (or **File \> Save As**), as shown in the following image.  
![](media/powerbi-desktop-query-overview/QueryOverview_SaveWork.png)

## More Information  
There are all sorts of things you can do with Power BI Desktop. For more information on its capabilities, check out the following resources:

-   [Getting Started with Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471664)

-   [Data Sources in Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471643)

-   [Connect to Data in Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471635)

-   [Shape and Combine Data with Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471644)

-   [Common Query Tasks in Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471648)  

Want to give us feedback? Great – use the **Send Feedback** menu item in Power BI Desktop. We look forward to hearing from you!  
![](media/powerbi-desktop-query-overview/SendFeedback.png)  
