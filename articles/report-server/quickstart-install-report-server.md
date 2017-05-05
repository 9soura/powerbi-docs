<properties
   pageTitle="Quickstart: Install Power BI Report Server"
   description="Installing Power BI Reports Server itself is very quick. From downloading, to installing and configuring, you should be up and running within a few minutes."
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
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
   ms.date="05/05/2017"
   ms.author="asaxton"/>
# Quickstart: Install Power BI Report Server

Installing Power BI Reports Server itself is very quick. From downloading, to installing and configuring, you should be up and running within a few minutes.

This is a quick look at how to install a report server if you just want to get up and running with a new server. For more detail information on installing a report server, see [Installing a Power BI Report Server](install-report-server.md).

## Step 1: Download

Download the install files, for Power BI Report Server, locally. To download Power BI Report Server, go to the [Microsoft download center](https://go.microsoft.com/fwlink/?linkid=839351).

![Download Power BI Report Server](media/quickstart-install-report-server/pbireportserver-install.png)

## Step 2: Run installer

Run the PowerBIReportServer.exe file that was download and step through the installation screens. You will have the opportunity to select the the installation path as well as select the edition you want to install. You can choose between an evaluation that expires within 180 days, a developer edition or the ability to provide a product key.

![Install Power BI Report Server](media/quickstart-install-report-server/pbireportserver-install.png)

## Step 3: Configure the server

After you are done installing, you will run the configuration manager to finish setting up your server. You will need to create a ReportServer catalog database as well as confirm the web portal and web service URLs.

![Configure Power BI Report Server](media/quickstart-install-report-server/pbireportserver-configure.png)

## Step 4: Browse to web portal

Now that you are configured, you should be able to browser to the web portal of your server. By default this will be `http://localhost/reports`. You will also be able to browse using the machine name, instead of using localhost, by default assuming you are not being blocked by any type of firewall.

![Power BI Report Server web portal](media/quickstart-install-report-server/web-portal.png)

## Next steps

[Administrator handbook]  
[Installing a Power BI Report Server](install-report-server.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)