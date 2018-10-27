---
title: "Enter data directly in a paginated report in Power BI Report Server | Microsoft Docs"
description: In this article, you see how you can enter data directly into a paginated report in Report Builder. 
author: maggiesMSFT
manager: kfile
ms.reviewer: ''

ms.service: powerbi
ms.component: report-builder
ms.topic: conceptual
ms.date: 10/26/2018
ms.author: maggies
---

# Enter data directly in a paginated report in Power BI Report Server

In this article, you learn about a feature in the new version of SQL Server 2016 Report Builder that lets you enter data directly into an RDL report as an embedded dataset.  This feature is similar to Power BI Desktop. You can type the data directly in a dataset in your report, or paste it in from another program like Microsoft Excel. After you've created a dataset by entering data, you can use it just like you would any other embedded dataset you've created. Plus you can add more than one table and join them in a query. This feature is especially useful for small, static datasets you might need to use in your report, like report parameters.
 
## Prerequisites

- To enter data directly in a paginated report, install the new version of [Report Builder from the Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613). 
- To save your paginated report to a report server, you need permissions to edit the RsReportServer.config file.

## Get started

After you’ve downloaded and installed Report Builder, you follow the same workflow you’ve previously used to add an embedded data source and dataset to your report. Under Data Sources, you see a new option, Enter Data.  You only need to set up this data source once in a report. After that, you can create multiple tables of entered data as separate datasets, all using that single data source.

1. In the **Report Data** pane, select **New** > **Dataset**.

    ![Report Builder New Dataset](media/paginated-reports-enter-data/paginated-new-dataset.png)

1. In the **Dataset Properties** dialog box, select **Use a dataset embedded in my report**.

1. Next to **Data source**, select **New**.

    ![New embedded data source](media/paginated-reports-enter-data/paginated-new-data-source.png)

1. In the **Data Source Properties** dialog box, select **Use a connection embedded in my report**.
2. In the **Select connection type** box, select **ENTER DATA** > **OK**.

    ![ENTER DATA data source](media/paginated-reports-enter-data/paginated-data-source-properties-enter-data.png)

1. Back in the **Dataset Properties** dialog box, select **Query Designer**.
2. In the **Query Designer** pane, click in the second row and type or paste your data in the table.

    ![Enter data in the Query Designer](media/paginated-reports-enter-data/paginated-enter-data.png)

    Or paste a table.

    ![Paste a table in the Query Designer](media/paginated-reports-enter-data/paginated-paste-data.png)

1. To set the column names, double-click each **NewColumn** and type the column name.

    ![Set column names](media/paginated-reports-enter-data/paginated-column-name.png)

    By default, the data type for each column is a String.  

9. To change the data type, if you want, right-click the column header > **Change Type**, and set it to another data type, such as Date or Integer.

    ![Change data type](media/paginated-reports-enter-data/paginated-data-type.png)

1. Delete that blank first row.
    
1. When you’ve finished creating the table, select **OK**.  

    ![XML data structure](media/paginated-reports-enter-data/paginated-xml-data.png)

    Notice the query that’s generated is the same as you’d see with an XML data source. Under the covers, that’s what we’re using as the data provider.  We’ve just re-purposed it to enable this scenario as well.

12. Select **OK**.

13. You see your data source and dataset in the **Report Data** pane.

    ![Dataset in Report Data pane](media/paginated-reports-enter-data/paginated-report-data-pane.png)

Now you can use your dataset as the basis for data visualizations in your report. You can also add another dataset and use the same data source for it.

## Upload the paginated report to a report server

You may want to upload your completed paginated report to a Power BI Report Server or SQL Server Reporting Services 2016 or 2017 report server. Before you do, you need to add the following item to your RsReportServer.config as an additional data extension. Back up your RsReportServer.config file before you make the change, in case you run into any issues.

```
<Extension Name=”ENTERDATA” Type=”Microsoft.ReportingServices.DataExtensions.XmlDPConnection,Microsoft.ReportingServices.DataExtensions”>
<Configuration>
<ConfigName>ENTERDATA</ConfigName>
</Configuration>
</Extension>
```

After you've edited it, here's what the list of data providers in the config file should look like:

![RsReportServer config file](media/paginated-reports-enter-data/paginated-rsreportserver-config-file.png)

That’s it – you can now publish reports that use this new functionality to your report server.

## Next steps

[What is Power BI Report Server?](report-server/get-started.md)
