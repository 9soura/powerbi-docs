﻿<properties
   pageTitle="Data sources supported by DirectQuery"
   description="Get a list of which data sources can use DirectQuery."
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
   ms.date="07/06/2017"
   ms.author="davidi"/>

# Data sources supported by DirectQuery

**Power BI Desktop** and the **Power BI service** have many data sources to which you can connect and get access to data. This article describes which data sources for Power BI support the connection method known as **DirectQuery**. For more information about DirectQuery, see [**DirectQuery in Power BI**](powerbi-desktop-directquery-about.md).

The following data sources support DirectQuery in Power BI:

-   Amazon Redshift
-   Azure HDInsight Spark (Beta)
-   Azure SQL Database
-   Azure SQL Data Warehouse
-   IBM Netezza (Beta)
-   Impala (version 2.x)
-   Oracle Database (version 12 and above)
-   SAP Business Warehouse (Beta)
-   SAP HANA
-   Snowflake
-   Spark (Beta)  (version 0.9 and above)
-   SQL Server
-   Teradata Database

Data sources that are have **(Beta)** or **(Preview)** after their name are subject to change, and are not supported for production use. They might also not be supported after publishing a report to the **Power BI service**, which means that  that opening a published report or exploring the dataset can result in an error.

The only difference between **(Beta)** and **(Preview)** data sources is that **(Preview)** sources must be enabled as a Preview feature before they become available for use. To enable a **(Preview)** data connector, in **Power BI Desktop** go to **File > Options and Settings**, and then **Settings > Options > Preview features**.


## On-premises gateway requirements

The following table specifies whether an **On-premises data gateway** is required to connect to the specified data source, after publishing a report to the **Power BI service**.

|Source |Gateway required?|
|---|---|
|SQL Server|Yes|
|Azure SQL Database|No|
|Azure SQL Data Warehouse|No|
|SAP HANA|Yes|
|Oracle Database|Yes|
|Teradata Database|Yes|
|Amazon Redshift|No|
|Impala (version 2.x)|Yes|
|Snowflake (Preview)|Not yet supported in the **Power BI service**|
|Spark (beta), version 0.9 and later|Not yet supported in the **Power BI service**|
|Azure HDInsight Spark (Beta)|Not yet supported in the **Power BI service**|
|IBM Netezza (Beta)|Not yet supported in the **Power BI service**|
|SAP Buisness Warehouse (Beta)|Not yet supported in the **Power BI service**|


## More Information

For more information about DirectQuery, check out the following resources:

-   [DirectQuery in Power BI](powerbi-desktop-directquery-about.md)

-   [DirectQuery and SAP HANA](powerbi-desktop-directquery-sap-hana.md)

-   [DirectQuery and SAP BW](powerbi-desktop-directquery-sap-bw.md)

-   [On-premises data gateway](powerbi-gateway-onprem.md)
