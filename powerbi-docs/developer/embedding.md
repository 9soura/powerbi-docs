---
title: Embedding with Power BI
description: Power BI offers APIs for embedding your dashboards and reports into applications.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: overview
ms.date: 07/31/2018
ms.author: maghan
---

# Embedding with Power BI
The Power BI service (SaaS) and the Power BI Embedded service in Azure (PaaS) have APIs for embedding your dashboards and reports. This means you have a set of capabilities and access to the latest Power BI features – such as dashboards, gateways and app workspaces – when embedding your content.

You can go through the [Onboarding experience tool](https://aka.ms/embedsetup) to quickly get started and download a sample application.

Choose the solution that is right for you:

* [Embedding for your organization](embedding.md#embedding-for-your-organization) allows you to extend the Power BI service. Run the [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData) solution.
* [Embedding for your customers](embedding.md#embedding-for-your-customers) provides the ability to embed dashboards and reports to users who don't have an account for Power BI. Run the [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData) solution.

![PBIE sample](media/what-can-you-do/what-can-you-do-02.png)

## Using APIs
There are two main scenarios when embedding Power BI content.  Embedding for users in your organization (who have licenses for Power BI) and embedding for your users and customers without requiring them to have Power BI licenses. The Power BI REST API allows for both scenarios.

For customers and users without Power BI licenses, you can embed dashboards and reports into your custom application, using the same API to either service your organization or your customers. Your customers see the data that is managed by the application. Also, for Power BI users in your organization, they'll have the additional options to view *their data* directly in Power BI or the context of the embedded application. You can take full advantage of the JavaScript and REST APIs for your embedding needs.

To view a sample of how embedding works, see the [JavaScript embed sample](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## Embedding for your organization
**Embedding for your organization** allows you to extend the Power BI service. This requires that users of your application sign into the Power BI service when they want to view their content. Once someone in your organization signs in, they will only have access to dashboards and reports that they own or that have been shared with them in the Power BI service.

*Examples of embedding for your organization include internal web application, the SharePoint Online web part and [Microsoft Teams integration (you must have Admin rights)](https://powerbi.microsoft.com/en-us/blog/power-bi-teams-up-with-microsoft-teams/).*

For embedding for your organization, see the following:

* [Integrate a report into an app](embed-sample-for-your-organization.md)

Self-service capabilities, such as edit, save and more, are available through the [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) when embedding for Power BI users.

You can go through the [Onboarding experience tool](https://aka.ms/embedsetup/UserOwnsData) to embed for your organization to quickly get started and download a sample application that walks you through integrating a report for your organization.

## Embedding for your customers
**Embedding for your customers** provides the ability to embed dashboards and reports to users who don't have an account for Power BI. Your customers don't need to know anything about Power BI. At least one Power BI Pro account is needed to create an embedded application. The Power BI Pro account acts as a master account for your application. Think of this as a proxy account. The Power BI Pro account also allows you to generate embed tokens that provide access to dashboards and reports within the Power BI service that are owned/managed by your application.

**Power BI Embedded** offers independent software vendors (ISVs) and developers the ability to embed for customers to quickly add stunning visuals, reports, and dashboards into applications through a capacity-based, hourly metered model.

![Embedding flow for embedding for your customers](media/embedding/powerbi-embed-flow.png)

Power BI Embedded has benefits for an ISV, their developers, and customers. For example, an ISV can start creating visuals for free with Power BI Desktop. ISVs can achieve faster time to market by minimizing visual analytic development efforts and stand out among the competition with differentiated data experiences. ISVs also can opt to charge a premium for the additional value created with embedded analytics.

Developers can spend time focused on building the core competency of their application rather than spending time developing visuals and analytics. Developers can rapidly meet customer report and dashboard demands and can embed easily with fully documented APIs and SDKs. Lastly, by enabling easy-to-navigate data exploration in their apps, ISVs allow their customers to make quick, data-driven decisions in context and with confidence from any device.

*An example of embedding for your customers is an ISV application sold to other companies.*

To embed dashboards, reports, and tiles, you would use the same APIs that you would use for embedding for your organization.

> [!IMPORTANT]
> While embedding has a dependency on the Power BI service, there is not a dependency on Power BI for your customers. They do not need to sign up for Power BI to view the embedded content in your application.

When you are ready to move to production, your app workspace assignment to a dedicated capacity is required. Power BI Embedded, within Microsoft Azure, offers dedicated capacities to use with your applications.

For details on how to embed, see [How to embed your Power BI dashboards, reports and tiles](embed-sample-for-customers.md).

You can go through the [Onboarding experience tool](https://aka.ms/embedsetup/AppOwnsData) to quickly get started and download a sample application that walks you through integrating a report into your application.

If you were using the Power BI Workspace Collections service within Azure, see [Migrate content from the Power BI Workspace Collections Azure service](migrate-from-powerbi-embedded.md) for information on how to migrate your content over.

## Next steps
You can now try to embed Power BI content into an application, or try to embed Power BI content for your customers.

> [!div class="nextstepaction"]
> [Embed for your organization](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
>[Embed for your customers](embed-sample-for-customers.md)

More questions? [Try asking the Power BI Community](http://community.powerbi.com/)