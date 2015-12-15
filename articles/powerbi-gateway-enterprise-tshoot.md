<properties
pageTitle="Troubleshoot the enterprise gateway"
description="Troubleshooting the enterprise gateway"
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="mblythe"
editor=""/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="12/01/2015"
ms.author="asaxton"/>
# Troubleshooting the Power BI Gateway - Enterprise (Preview)

## Configuration

**Collecting logs from the gateway configurator**

You can start the configurator in a debug mode which will collect logs which can be used to troubleshoot issues when trying to configure the gateway. From a command prompt, pass */troubleshoot* to the configurator when you launch it. The default path for the configurator is the following.

    C:\Program Files\Power BI Enterprise Gateway

The command line would look something like this.

    EnterpriseGatewayConfigurator.exe /troubleshoot
	
On the dialog screen, you will see a gear icon in the upper right.

![](media/powerbi-gateway-enterprise-tshoot/egw-tshoot1.png)
  
After you walk through the steps, and close the configurator, it will place a zip file on the desktop. It may take a minute for the zip file to show. This zip file will contain several log files which can be used to diagnose further. The file name will look like the following.

    EnterpriseGatewayLogs 2015-12-01T14_39_32.zip

**Error: Failed to create gateway. Please try again.**

All of the details are available, but the call to the Power BI service returned an error.  The error, and an activity id, will be displayed. This could happy for different reasons. You can collect, and review, the logs as mentioned above to get more details. 

This could also be due to proxy configuration issues. The user interface does now allow for proxy configuration. You would need to modify the *enterprisegatewayconfigurator.exe.config* with the correct proxy information. [Learn more](https://msdn.microsoft.com/library/kd3cf2ex(v=vs.110).aspx)

**Error: Failed to update gateway details.  Please try again.**

Information was received from the Power BI service, to the gateway. The information was passed onto the local windows service, but it failed to return. Or, a symmetric key generation failed. The inner exception will be displayed under **Show details**. You can collect, and review, the logs as mentioned above to get more details. 

**Error: Power BI service reported local gateway as unreachable. Please restart the gateway and try again.**

At the end of configuration, the Power BI service will be called again to validate the gateway. The Power BI service does not report the gateway as *live*. Restarting the windows service may allow the communication to be successful. You can collect, and review, the logs as mentioned above to get more details. 

## Data sources

**Error: Unable to Connect. Details: "Invalid connection credentials"**

Within **Show details**, it should display the error message received from the data source. For SQL Server, you should see something like the following.

    Login failed for user 'username'.

Verify that you have the correct username and password. Also verify that those credentials can successfully connect to the data source. Make sure the account being used matches the **Authentication Method**.

**Error: Unable to Connect. Details: "Cannot connect to the database"**

We were able to connect to the server, but not to the database supplied. Verify the name of the database, and that the user credential as the proper permission to access that database.

Within **Show details**, it should display the error message received from the data source. For SQL Server, you should see something like the following.

    Cannot open database "AdventureWorks" requested by the login. The login failed. Login failed for user 'username'.

**Error: Unable to Connect. Details: "Unknown error in enterprise gateway"**

This error could occur for different reasons. Be sure to validate that you can connect to the data source from the machine hosting the gateway. This could be the result of the server not being accessible.

Within **Show details**, you will see an error code of **DM_GWPipeline_UnknownError**.

You can also look in the Event Logs > **Applications and Services Logs** > **Power BI Enterprise Gateway Service** for more details.

## See Also

[Power BI Gateway – Enterprise (Preview)](powerbi-gateway-enterprise.md)

[Power BI Gateway - Enterprise (Preview) in-depth](powerbi-gateway-enterprise-indepth.md)

[Manage your enterprise data source - SQL Server](powerbi-gateway-enterprise-manage.md)

[Tools for troubleshooting refresh issues](powerbi-refresh-tools-for-troubleshooting-issues.md)