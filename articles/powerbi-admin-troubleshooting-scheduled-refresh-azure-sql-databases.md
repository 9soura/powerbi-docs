﻿<properties 
   pageTitle="Troubleshooting scheduled refresh for Azure SQL Databases"
   description="Troubleshooting scheduled refresh for Azure SQL Databases in Power BI"
   services="powerbi" 
   documentationCenter="" 
   authors="guyinacube" 
   manager="mblythe" 
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
   ms.date="03/04/2016"
   ms.author="asaxton"/>

# Troubleshooting scheduled refresh for Azure SQL Databases in Power BI  

For detailed steps on setting up scheduled refresh, be sure to see [Refresh data in Power BI](powerbi-refresh-data.md).

While setting up scheduled refresh for Azure SQL Database, if you get an error with error code 400 during editing the credentials, try the following to set up the appropriate firewall rule:

1.  Log into your Azure management portal

2.  Go to the Azure SQL server you are configuring refresh for

3.  Turn on 'Windows Azure Services' in the allowed services section

![](media/powerbi-admin-troubleshooting-scheduled-refresh-azure-sql-databases/Azurerefresh.png)  