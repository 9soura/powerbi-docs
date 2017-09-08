﻿<properties
   pageTitle="Connect to a Snowflake computing warehouse in Power BI Desktop (Preview)"
   description="Easily connect to and use a Snowflake computing warehouse in Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
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
   ms.date="09/06/2017"
   ms.author="davidi"/>

# Connect to Snowflake in Power BI Desktop (Preview)

In Power BI Desktop, you can connect to a **Snowflake** computing warehouse and use the underlying data just like any other data source in Power BI Desktop. This release of the **Snowflake** connector is in Preview, and is subject to change.

## Enable the Snowflake (Preview) feature

To get access to the **Snowflake** connector, you first need to enable this preview feature. In **Power BI Desktop**, select **File > Options and settings > Option** then in the **Options** window, select the **Preview Features** section and enable **Snowflake**, as shown below.

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_1.png)

When you check that box, you turn on the **Snowflake** preview feature. You'll need to restart Power BI Desktop for the change to take effect. Once you do, the preview feature is available.

You also *must* install the **Snowflake ODBC driver** on computers that use the **Snowflake** connector, using the architecture that matches the installation of **Power BI Desktop**, either 32-bit or 64-bit. Just follow the following link and [download the appropriate Snowflake ODBC driver](http://go.microsoft.com/fwlink/?LinkID=823762).

## Connect to a Snowflake computing warehouse

Once you've enabled to preview feature, to connect to a **Snowflake** computing warehouse select **Get Data** from the **Home** ribbon in Power BI Desktop. Select **Database** from the categories on the left, and you see **Snowflake (Beta)**.

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_2.png)

In the **Snowflake** window that appears, type or paste the name of your Snowflake computing warehouse into the box and select **OK**. Note that you can choose to **Import** data directly into Power BI, or you can use **DirectQuery**. You can learn more about [using DirectQuery](powerbi-desktop-use-directquery.md).

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_3.png)

When prompted, put in your username and password.

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_4.png)

>**Note:** Once you put in your username and password for a particular **Snowflake** server, Power BI Desktop uses those same credentials in subsequent connection attempts. You can modify those credentials by going to **File > Options and settings > Data source settings**.

Once you successfully connect, a **Navigator** window appears and displays the data available on the server, from which you can select one or multiple elements to import and use in **Power BI Desktop**.

![](media/powerbi-desktop-connect-snowflake/connect_snowflake_5.png)

You can **Load** the selected table, which brings the entire table into **Power BI Desktop**, or you can **Edit** the query, which opens **Query Editor** so you can filter and refine the set of data you want to use, and then load that refined set of data into **Power BI Desktop**.

## More Information

﻿There are all sorts of data you can connect to using Power BI Desktop. For more information on data sources, check out the following resources:

-   [Getting Started with Power BI Desktop](powerbi-desktop-getting-started.md)

-   [Data Sources in Power BI Desktop](powerbi-desktop-data-sources.md)

-   [Shape and Combine Data with Power BI Desktop](powerbi-desktop-shape-and-combine-data.md)

-   [Connect to Excel workbooks in Power BI Desktop](powerbi-desktop-connect-excel.md)   

-   [Enter data directly into Power BI Desktop](powerbi-desktop-enter-data-directly-into-desktop.md)   
