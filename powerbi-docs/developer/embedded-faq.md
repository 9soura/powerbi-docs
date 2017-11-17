---
title: Frequently asked questions about Power BI Embedded
description: Browse a list of frequently asked questions and answers about Power BI Embedded.
services: powerbi
documentationcenter: ''
author: guyinacube
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''

ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/17/2017
ms.author: asaxton
---
# Frequently asked questions about Power BI Embedded

* If you have other questions, [try asking the Power BI Community](http://community.powerbi.com/).
* Still have an issue? Please visit the [Power BI support page](https://powerbi.microsoft.com/support/).

## General

### What is Power BI Embedded?

Microsoft Power BI Embedded allows application developers to embed stunning, fully interactive reports, dashboards and tiles into applications without the time and expense of building their own data visualizations and controls from the ground-up.

### Who is the target audience for Power BI Embedded?

Developers and software companies making their own applications referred to as independent software vendors (ISVs).

### How is Power BI Embedded different from Power BI the service?

Power BI Embedded is intended for ISVs or developers who are building applications and want to embed visuals into those applications to help their customers make decisions without building an analytics’ solution from the ground up. Embedded analytics enables business users to access the business data and perform queries to generate insights using this data within the application.

Power BI, on the other hand, is a software-as-a-service analytics solution that gives organizations a single view of their most critical business data.

### What is the difference between Power BI Premium and Power BI Embedded?

Power BI Premium is capacity geared toward enterprises, who want a complete BI solution that provides a single view of its organization, partners, customers, and suppliers. Power BI Premium helps your organization make decisions. Power BI Premium is a SaaS product and comes with the ability for users to consume content through the Power BI portal, mobile app, and through internally developed apps.

Power BI Embedded is for ISVs or developers who are building applications and want to embed visuals into those applications. Power BI Embedded helps your customers make decisions because Power BI Embedded is for application developers, customers of that application can consume content stored on Power BI Embedded capacity, including anyone inside or outside the organization. Power BI Embedded capacity content cannot be shared through one-click publish to Web or one-click publish to SharePoint, and it does not support SSRS reports.

### What is the Microsoft recommendation for when a customer should buy Power BI Premium vs Power BI Embedded?

The recommendation of Microsoft is that enterprises buy Power BI Premium, an enterprise-grade, self-service cloud BI solution, and ISVs buy Power BI Embedded, cloud-powered embedded analytics components. However, there are no restrictions on which product a customer can buy.

There may be some cases where an ISV (typically large) wants to use a P SKU to get the additional benefits of the pre-packaged Power BI service within their organization as well as embed in their applications. And of course, some Enterprises may decide to use A SKUs in Azure if they are only interested in building line of business applications and embedding analytics into them and are not interested in using the pre-packaged Power BI service.

### When will Power BI Embedded be available in Azure?

Power BI Embedded is now available.

## Technical

### What is the difference between the A SKUs in Azure and EM SKUs in Office 365?

PowerBI.com is an enterprise solution that includes many capabilities like social collaboration, email subscription, etc. in a Software as a Service offering

Power BI Embedded is a set of APIs available for developers to create an embedded analytics solution in a Platform as a Service offering. For the Embedded analytics scenario, PowerBI.com should be used to help ISVs and developers manage their embedded analytics solution content and tenant level settings.

Here is a partial list of differences you may use with each.

|Feature  |Power BI Embedded<br>(A SKUs) |Power BI Premium Capacity<br>(EM SKUS)  |
|---------|---------|---------|
|Embed artifacts from a Power BI App workspaces     |Azure capacity |Office 365 capacity |
|Power BI license required to consume reports |No  |Yes |
|Consume Power BI reports in an Embedded application |Yes  |Yes |
|Consume Power BI reports in SharePoint |No |Yes |
|Consume Power BI reports in Teams |No |Yes |

### Power BI now offers three SKUs for embedding: A SKUs, EM SKUs and P SKUs. Which one should I purchase for my scenario?

|  |A SKU (Power BI Embedded)  |EM SKU (Power BI Premium)  |P SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|Purchase     |Azure portal |Office |Office |
|Use cases |* Embed content in your own application |* Embed content in your own application<br>* Share content with Power BI FREE users outside PowerBI.com and embed in other SaaS applications (SharePoint, Teams) |* Embed content in your own application<br>* Share content with Power BI FREE users outside PowerBI.com and embed in other SaaS applications (SharePoint, Teams)<br>* Share content with Power BI FREE users through PowerBI.com  |
|Billing |Hourly |Monthly |Monthly |
|Commitment  |No commitment |Yearly  |Monthly/Yearly |
|Differentiation |Full elasticity- can scale up/ down, pause/ resume resources in Azure portal or through API  |Can be used to embed content in SharePoint Online and Microsoft Teams |Combine embedding in applications and use the Power BI Service in the same capacity |

### How can I monitor capacity consumption?

Monitoring through Azure is on the near-term roadmap. The Azure resource, Power BI Embedded, will include monitoring KPIs that will show health, and usage.

### Will my capacity scale automatically to adjust to the consumption of my app?

While there is no automated scaling now, all the APIs are available to scale at any time.

### What is the authentication model for Power BI Embedded?

Power BI Embedded will continue to use Azure AD for authentication of the master user (a designated Power BI Pro licensed user), authenticating the application inside Power BI.

The authentication and authorization of the application users will be implemented by the ISV, the ISV can implement their own authentication for their applications.

If you already have an Azure AD tenant, you can use your existing directory, or you can create a new Azure AD tenant for your embedded application content security.

### How is Power BI Embedded different from other Azure services?

The ISV/developer must have a Power BI account before the purchase of Power BI Embedded in Azure. Your Power BI Embedded deploy region is determined by your Power BI account. Manage your Power BI Embedded resource in Azure to:

* Scale up/down
* Add capacity admins
* Pause/resume of service

Use PowerBI.com to assign/un-assign workspaces to your Power BI Embedded capacity.

### What deploy regions are supported?

Australia Southeast, Brazil South, Canada Central, East US 2, India West, Japan East, North Central US, North Europe, South Central US, Southeast Asia, UK South, West Europe, West US, and West US 2.

## Licensing

### How do I purchase Power BI Embedded?

Power BI Embedded is available through Azure.

### How Power BI Embedded be metered?

Power BI Embedded will have an hourly meter.

### How does the usage of Power BI Embedded show up on my bill?

Power BI Embedded bills on a predictable hourly rate based on the type of node(s) deployed.

### What happens if I already purchased Power BI Premium and now I want some of the benefits of Power BI Embedded in Azure?

Customers will continue to pay for any existing Power BI Premium purchases until the end of their current agreement term and then may switch their Power BI Premium purchases as necessary at that point.

### Do I still have to buy Power BI Premium to get access to Power BI Embedded?

No, Power BI Embedded includes the Azure based capacity that you need to deploy and distribute your solution to customers.

### Who needs a Power BI Pro license for Power BI Embedded and why?

It is required that any analyst that needs to add reports to a Power BI workspace, any developer that requires use of the REST APIs, any tenant admin that needs to manage the Power BI tenant and capacity will need a Power BI Pro license.

Because Power BI Embedded allows use of the Power BI portal for managing and validating embedded content, the Power BI Pro license is required to authenticate the App inside PowerBI.com to get access to the reports in the right repositories.

### Can I get started for free?

Yes, you can use your [Azure credits](https://azure.microsoft.com/free/) for Power BI Embedded.

### Can I get a trial experience for Power BI Embedded in Azure?

Since Power BI Embedded is a part of Azure it is possible to use the service with the [$200 credit received when signing up for Azure](https://azure.microsoft.com/free/).

### What’s the purchase commitment for Power BI Embedded? 

Customers may change their usage on an hourly basis. There is no monthly or annual commitment for the Power BI Embedded service.

### Where is Power BI Embedded available? US Government? Germany? China? What is the timing?

Power BI Embedded will be available in Azure commercial clouds at GA.  Sovereign cloud availability will be added in the future.

### Is Power BI Embedded available for non-profits and educational?

Non-profit and educational entities can purchase Azure. There is no special pricing for these types of customers in Azure.

More questions? [Try the Power BI Community](http://community.powerbi.com/)