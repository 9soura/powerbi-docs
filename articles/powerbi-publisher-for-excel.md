<properties
   pageTitle="Power BI Publisher for Excel"
   description="Learn how to use the Power BI Publisher for Excel"
   services="powerbi"
   documentationCenter=""
   authors="Minewiskan"
   manager="mblythe"
   editor=""
   tags=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="01/12/2016"
   ms.author="owend"/>
# Power BI Publisher for Excel (Preview)

With Power BI Publisher for Excel, you can take snapshots of your most important insights in Excel, like PivotTables, Charts, and ranges and pin them to dashboards in Power BI.

![](media/powerbi-publisher-for-excel/pbi_excel_publisher_pinobj_dashboard.png)

What can you pin? Just about anything in an Excel worksheet. You can select a range of cells from a simple sheet or table, a PivotTable or PivotChart, illustrations and images, text.
What you can't pin: You cannot pin 3D Maps or visualizations in Power View sheets. There are also some objects you can pin, but it wouldn't make much sense to, like a Slicer or Timeline filter.

When you pin an object from Excel, a new tile is added to a new or existing dashboard in Power BI. The new tile is a snapshot, so it's not dynamic, but you can still update it. For example, if you make a change to a PivotTable you've already pinned, the dashboard tile in Power BI isn't updated automatically. You can update your pinned objects in Power BI by using Pin Manager. You'll learn more about Pin Manager below.

## Download and install
Power BI Publisher for Excel is an add-in you can download and install on desktop versions of Microsoft Excel 2010 and later.

-   [Power BI Publisher for Excel 64-bit version](http://go.microsoft.com/fwlink/?LinkId=715729)
-   [Power BI Publisher for Excel 32-bit (x86) version](http://go.microsoft.com/fwlink/?LinkId=715730)

Once you have the publisher installed, you'll see a new **Power BI**
ribbon in Excel, where you can sign in to and out of Power BI, pin objects to a dashboard, and manage objects you've already pinned.

![](media/powerbi-publisher-for-excel/pbi_excel_publisher_ribbon.png)

The Power BI Publisher add-in is enabled by default, but if for some reason you don't see the Power BI ribbon tab in Excel, you'll need to enable it. Click **File** > **Options** > **Add-ins** > **COM Add-ins**. Select **Microsoft Power BI Publisher for Excel**.

## Pin a range to a dashboard
You can select any range of cells from your worksheet and pin a snapshot to an existing or new dashboard in Power BI.
1. In your worksheet, select a range, and then click Pin. If you're not already signed into Power BI, you'll need to now.
2. In Pin to Dashboard, select an existing dashboard or create a new one, and then click Pin ![](media/powerbi-publisher-for-excel/pbi_publisher_pinrange.gif).


## Pin a Chart to a dashboard
Just click on the chart, and then click Pin ![](media/powerbi-publisher-for-excel/pbi_excel_publisher_pin.png).

![](media/powerbi-publisher-for-excel/pbi_excel_publisher_chart.png)


## Manage pinned objects
With Pin Manager, you can update (refresh) a pinned object's associated tile in Power BI. You can also remove the pin between an object you've already pinned to dashboards in Power BI.

![](media/powerbi-publisher-for-excel/pbi_excel_publisher_pin_manager.png)

To update a tile in your dashboard, in Pin Manager, select the object and then click **Update**.

To remove the mapping between a pinned object in Excel and the associated tile in a dashboard, click **Remove**. When you click Remove, you're not removing the object from your worksheet in Excel or deleting the associated tile in the dashboard. You are removing the pin, or mapping, between them. The object will no longer appear in Pin Manager. If you pin the object again, it will appear as a new tile.

To remove a pinned object (a tile) from a dashboard, you'll need to that in Power BI. In the tile you want to delete, click the **Open menu** icon ![](media/powerbi-publisher-for-excel/pbi_excel_publisher_tile_openmenu.png)
and then click **Delete tile**   ![](media/powerbi-publisher-for-excel/pbi_excel_publisher_tile_trashcan.png).

## A few things to know
Waiting for known issues from Aviv.
