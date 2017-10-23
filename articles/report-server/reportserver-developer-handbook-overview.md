<properties
   pageTitle="Developer handbook overview, Power BI Report Server"
   description="Welcome to the developer handbook for Power BI Report Server, an on-premises location for storing and managing your Power BI, mobile, and paginated reports."
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
   ms.date="09/05/2017"
   ms.author="asaxton"/>

# Developer handbook overview, Power BI Report Server

Welcome to the developer handbook for Power BI Report Server, an on-premises location for storing and managing your Power BI, mobile, and paginated reports.

![](media/reportserver-developer-handbook-overview/admin-handbook.png)

This handbook will highlight options you have, as a developer, to work with Power BI Report Server.

## Embedding

For any report within Power BI Report Server, you can embed within an iFrame by adding the querystring parameter `?rs:Embed=true` to the URL. This works with Power BI reports as well as other report types.

### Report Viewer Control

For paginated reports, you can take advantage of the Report Viewer Control. This allows you to place the control within a .NET windows or web application. For more information, see [Get started with the Report Viewer Control](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started).

## APIs

You have several API options for interacting with Power BI Report Server. This includes the following.

* [SOAP APIs using the web services](https://docs.microsoft.com/sql/reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework)
* [URL Access](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)
* [WMI Provider](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

You can also use the open source [PowerShell untilies](https://github.com/Microsoft/ReportingServicesTools) to manage your report server.

> [AZURE.NOTE] The PowerShell utilities do not currently support Power BI Desktop files (.pbix).

## Custom extensions

The Extension Library is a set of classes, interfaces, and value types that are included in Power BI Report Server. This library provides access to system functionality and is designed to be the foundation on which Microsoft .NET Framework applications can be used to extend Power BI Report Server components.

There are several types of extensions you can build.

* Data processing extensions
* Delivery extensions
* Rendering extensions for paginated reports
* Security extensions

To learn more, see [Extension library](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library).

## Next steps

[Get started with the Report Viewer Control](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started)  
[Building Applications Using the Web Service and the .NET Framework](https://docs.microsoft.com/sql/reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework)  
[URL Access](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)  
[Extension library](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library)  
[WMI Provider](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

More questions? [Try asking the Power BI Community](https://community.powerbi.com/)

