<properties
   pageTitle="Connect to an Oracle database"
   description="Steps and downloads necessary to connect Oracle to Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
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
   ms.date="12/01/2016"
   ms.author="davidi"/>

# Connect to an Oracle database

In order to connect to an Oracle database with **Power BI Desktop**, the correct Oracle client software must be installed on the computer running Power BI Desktop. Which Oracle client software you use depends on which version of Power BI Desktop you have installed - the **32-bit** version or the **64-bit** version.

## Determining which version of Power BI Desktop is installed

To determine which version of Power BI Desktop is installed, select **File > About** then check the **Version:** line. In the following image, a 64-bit version of Power BI Desktop is installed:

![](media/powerbi-desktop-connect-oracle-database/connect-oracle-database_1.png)

## Installing the Oracle client

For **32-bit** versions of Power BI Desktop, use the following link to download and install the **32-bit** Oracle client:

-   [32-bit Oracle Data Access Components (ODAC) with Oracle Developer Tools for Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

For **64-bit** versions of Power BI Desktop, use the following link to download and install the **64-bit** Oracle client:

-   [64-bit ODAC 12c Release 4 (12.1.0.2.4) for Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## Connect to an Oracle database

Once the matching Oracle client driver is installed, you can connect to an Oracle database. Take the following steps to make the connection.

1.  From the Get Data window, select **Database > Oracle Database**

    ![](media/powerbi-desktop-connect-oracle-database/connect-oracle-database_2.png)

2.  In the **Oracle Database** dialog that appears, provide the name of the server, and select **Connect**. If a SID is required, you can specify that using the format: *ServerName/SID*.

    ![](media/powerbi-desktop-connect-oracle-database/connect-oracle-database_3.png)

3.  If you want to import data using a native database query, you can put your query in the **SQL Statement** box, available by expanding the **Advanced options** section of the **Oracle Database** dialog.

    ![](media/powerbi-desktop-connect-oracle-database/connect-oracle-database_4.png)

4.  Once your Oracle database information is entered into the Oracle Database dialog (including any optional information such as a SID or a native database query), select **OK** to connect.

5.  If the Oracle database requires database user credentials, input those credentials in the dialog when prompted.
