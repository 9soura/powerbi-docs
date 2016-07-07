<properties
   pageTitle="What's new in the Power BI service"
   description="What's new in the Power BI service"
   services="powerbi"
   documentationCenter=""
   authors="amandacofsky"
   manager="mblythe"
   backup="mihart"
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="06/06/2016"
   ms.author="amac"/>

# What's new in the Power BI service  

Check this page for known issues and recently-released features in **Power BI Service**.

>**NOTE**:
>
For related "What's New" information, see:
>
>[What's new in Power BI Desktop](powerbi-desktop-latest-update.md)  
>
>[What's new in the mobile apps for Power BI](powerbi-mobile-whats-new-in-the-mobile-apps.md)  
>
>[Power BI Developer blog](http://blogs.msdn.com/b/powerbidev/).



## Recent updates

**June 1, 2016**

-   Quick Insights work with Complex Filters: We are happy to announce that Quick Insights scoped to a single tile now understand complex filters. 

For all the details, [visit the Power BI Team blog](https://powerbi.microsoft.com/blog/smarter-auto-generated-insights-with-complex-filters/)

**May 16, 2016**

***Get Data***

-   File size limit increase to 1 GB: We increased the file size limit for both Excel workbooks and Power BI Desktop files to 1 GB.

-   Find SSAS servers set up with the Enterprise Gateway and other Gateway updates: Now when you set up an Enterprise Gateway, users in your company will be able to access these servers in the Power BI service through the Get Data page. We also added support for refreshing datasets that include data from SAP Business Warehouse Server using the gateway and creating UPN mapping rules when you are using Analysis Services with the gateway.

***Row-level security (RLS)***

-   Azure Active Directory (AAD) group support: Users can now assign AAD groups (security groups and distribution lists) to a role. This makes it easier to assign roles to a large group of users at once.

-   [Test your RLS roles with reports backed by the data with RLS in place](powerbi-admin-rls.md#test-the-role): We added a feature to our RLS preview that lets you test your dataset as a specific role. This will make sure the role works as you expect before any users get their hands on your dashboard.

-   Define and apply RLS to cloud models based on direct queries: You can now create and apply RLS rules for direct query data sources.

***Dashboards***

-   Favorite dashboards: To help you reach the dashboards you go to most, we added a way to favorite those dashboard and make them easily accessible from all your workspaces.

***Analyze in Excel***

-   Improved download experience: Easily download updates to the Analyze in Excel feature through a new dialog experience.

-   Support for RLS: Once you set up RLS, the rules you apply to the data now flow through when a user analyzes the data in Excel.

-   Improved error messaging for on-premises Analysis Services databases: Previously, if you selected Analyze in Excel for an unsupported data source, you wouldn't get an error message until after you downloaded the ODC file and tried to connect to Power BI. Now as soon as you select Analyze in Excel for a data source we don't support, you'll see a message letting you know we don't yet support that data source.

For all the details, [visit the Power BI Team blog](https://powerbi.microsoft.com/blog/power-bi-service-may-update-file-size-increase-to-1-gb/)

**May 13, 2016**

-   [Power BI Q&A support for SQL Server 2016 Analysis Services tabular models](powerbi-service-q-and-a-direct-query.md): We are pleased to announce improvements to the Power BI Q&A user experience and the start of the public preview for Power BI Q&A for enterprise gateway connected data sources - starting with support for SQL Server 2016 Analysis Services tabular models. For all the details, [see the blog post](https://powerbi.microsoft.com/blog/power-bi-q-a-for-enterprise-gateway-connected-data-sources-now-available-in-public-preview/)

-   [Local File Support for Excel Reports](powerbi-service-excel-workbook-files.md#local-excel-workbooks): You can now upload your Excel files from your local drive or other storage services and use that Excel Report just as you would in Excel Online with the added benefits of Power BI. For all the details, [see the blog post](https://powerbi.microsoft.com/blog/powerbi-upload-excel-reports-from-local-files/)

**April 28, 2016**

-   [Quick Insights on Dashboard Tiles](powerbi-service-auto-insights.md#run-quick-insights-on-a-dashboard-tile): When viewing a tile in Focus mode, click Get Insights to search the tile and its related data for correlations, outliers, trends, seasonality, change points in trends, and major factors automatically, within seconds.

For all the details, [visit the Power BI Team blog](https://powerbi.microsoft.com/blog/find-more-insights-in-your-dashboards-with-quick-insights/)

**April 26, 2016**

-   Narratives for Power BI: As you interact with your data and visualizations, this custom visual dynamically delivers insights in narrative form, just like you'd expect an analyst would write. This visual is fueled by [Narrative Science Quill](https://www.narrativescience.com/quill).

For all the details, [visit the Power BI Team blog](https://powerbi.microsoft.com/blog/get-natural-language-narratives-in-power-bi-reports/)

**April 16, 2016**

-   Microsoft Trust Center: Power BI joined the Microsoft Trust Center, a single source for documenting compliance certifications for Microsoft products. Power BI's certifications include ISO 27001, ISO 27018, EU Model Clauses, HIPAA BAA, and UK G-Cloud.

For all the details, [visit the Power BI Team blog](https://powerbi.microsoft.com/blog/power-bi-added-to-microsoft-trust-center/)

**April 14, 2016**

***Enterprise***

-   [ExpressRoute](powerbi-admin-power-bi-expressroute.md): use to establish a private, managed connection to Power BI.

-   [Content pack support for RLS](powerbi-admin-rls.md) (Preview): If RLS is defined for those dashboards and reports that are distributed as part of a content pack, then the security rules will be respected for those content packs.

***Dashboards***

-   [Vimeo video tile](powerbi-service-add-a-widget-to-a-dashboard.md):  From the dashboard, add a tile that contains an embedded Vimeo player.

***Analyze in Excel***

-   [Analyze in Excel](powerbi-service-analyze-in-excel.md) available to all users: the ability to access your Power BI data models in Excel has been extended to all users; free and Pro.

-   Improved multi-user account experience: if you have more than 1 Power BI user account, it's now easier to sign-in.


For all the details, [visit the Power BI Team blog](https://powerbi.microsoft.com/blog/power-bi-service-april-update-expressroute-for-power-bi/)

**March 31, 2016**
Lots of updates announced at the Microsoft Data Insights Summit.

***Dashboards***

-   Featured dashboard: makes it easier to reach the dashboard you care about most.

-   Filter dashboard list: show all, show content you created, show content shared with you.


***Enterprise features***

-   Admin usage reporting: added a usage report to the Power BI admin center.

-   Row-level security: this is a Preview feature that allows you to set permissions on Power BI datasets.

-   Disable exporting data: users in your tenant will no longer be able to export tile and visual data to a .csv file.

***Q&A***

-   Auto complete for "is": Q&A will suggest values if you type column name followed by "is".

***Mobile***

-   KPIs on your Apple watch: monitor your KPI and card tiles without having to open Power BI app.

***Excel***

-   Analyze in Excel: connect your Power BI data model to Excel and do your analysis inside of Excel instead of Power BI.

***Other***

-   Power BI in Australia: now anyone in Australia, individual or through an organization, can go to powerbi.microsoft.com and sign up for Power BI.

-   Language settings: override the automatic language detection and set the language for Power BI.

For all the details, [visit the Power BI Team blog](https://powerbi.microsoft.com/blog/power-bi-service-march-update-part-two/)

**March 11, 2016**

This month we made some updates to dashboards, Quick Insights, and Q&A.

***Dashboards***

-   Full Screen mode: print without having to exit Full Screen mode first

-   Full Screen mode: expand your tiles to fill the entire canvas and remove excess white space by selecting **Fit to Width**

-   Use Tile Flow to automatically align your tiles to the top left corner of the canvas.

***Quick Insights***

-   The Trend and Correlaction insights now have trend lines to make it easier to see patterns in the data.

***Q&A***

-   You can now specify Gauge and Area charts in Q&A

-   Improved auto-complete for Q&A - as soon as you type just a few characters, Q&A begins auto completing and suggesting visuals for you.


For all the details, [visit the Power BI Team blog](https://powerbi.microsoft.com/blog/power-bi-service-march-update/)




**February 10, 2016**

Today we released a long list of top-requested features. [Read the blog post](https://powerbi.microsoft.com/blog/power-bi-february-service-update/).

***Sharing***

- Share with users outside your organization

- Request access to a dashboard

***Admin Portal***

- Easy user management with a link to the O365 Admin Center

- Ability to disable publish to web

- Prevent users from publishing content packs to the entire org

- Ability to disable sharing content to external users

***Quick Insights***

- Quick Insights when you publish Power BI Desktop files

***Dashboard***

- Add Web content to your dashboard (via Widget)
- Add video content to your dashboard (via Widget)
- Zoom on dashboards

***Connectivity***
- Connect to files on your team SharePoint site through a URL

For all the details, [visit the Power BI Team blog](https://powerbi.microsoft.com/blog/power-bi-february-service-update/)

**January 28, 2016**

Updates to reports and visualizations:

- [Add borders to visuals](https://powerbi.microsoft.com/blog/power-bi-updates-this-week-new-report-authoring-capabilities/#borders)

- [Add background images to pages and Cartesian chart plot areas](
https://powerbi.microsoft.com/blog/power-bi-updates-this-week-new-report-authoring-capabilities/#background)

Performance Improvements for report rendering, cross-highlight, etc.

- Regardless of the browser version being used, a significant Performance improvement can be noticed by users when loading reports, switching between pages, cross-highlighting data across visuals, etc. with this new update.


**January 6, 2016**

The Power BI team has been busy over the holiday break. For all the details, [visit the Power BI Team blog](http://blogs.msdn.com/b/powerbi/archive/2016/01/06/power-bi-service-update-0106.aspx)

***Dashboards***

- Export tile data

- Add an image or text box widget to dashboards

- Print dashboards

- Refresh time on tiles

- Tooltips on dashboard tiles

***Collaboration***

- Shared dashboard notification

- Contact owner of a shared or organizational dashboard

***Reports***

- Print current report page

- Export report visual data

***Connectivity***

- Connect to files on SharePoint team sites

***Excel Reports***

- Open Excel reports in Excel desktop

- Pin Excel charts

- Format improvements for Excel tiles

***Other***

- Power BI in Brazil

- Hebrew and Arabic support

For all the details, [visit the Power BI Team blog](http://blogs.msdn.com/b/powerbi/archive/2016/01/06/power-bi-service-update-0106.aspx)


**December 16, 2015**

Lots of updates this week, most apply to Power BI Desktop but several significant updates to report authoring and visualizations as well. The [Power BI Team Blog](http://blogs.msdn.com/b/powerbi/archive/2015/12/16/more-power-bi-feature-updates-power-bi-desktop-december-update-and-new-power-bi-service-features.aspx) contains full descriptions and even a video describing the updates.   

[Download Power BI Desktop](https://powerbi.microsoft.com/desktop?WT.mc_id=Blog_Desktop_Update)

* Updates to the report authoring formatting pane and ribbon:

  1. Format data labels per category series

  2. Change number of decimal places showed in visuals

  3. Change text size in visuals

  4. Ability to lay out visuals accurately: alignment, distribute, size, position (requires Power BI Desktop for authoring)

  5. Set styles across multiple visuals through Format Painter (requires Power BI Desktop for authoring)

* Enhancements to visualizations:

  1. visuals cue for sort state in Table visual

  2. new visual: Stacked Area chart

  3. smart tooltips for Area and Line charts on hover

  4. ability to create Reference line/region for a Cartesian visual

  5. improved data labels for pie and scatter chart

* R visuals integration in Desktop (Preview feature)

* Desktop will suggest table to table relationships when trying to create 2 tables which are not related.

* Desktop optimized Home ribbon layout.

* Desktop data modeling updates in Relationships View:

  1. zooming slider

  2. fit zoom to

  3. reset layout

  4. ability to zoom in using Ctrl-Mouse selection rectangle

* Desktop data connectivity enhancements

  1. SSAS Multidimensional support - Hierarchies support (Preview Feature)

  2. Stripe Connector

  3. Smartsheet Connector

  4. “Enter Data”: Paste or enter data to create a table

  5. DirectQuery Improvements:  Support for all data types of T-SQL and SAP HANA, resulting in Performance improvements.

  6. ODBC Connector: Support for selecting User/System DSNs

  7. CSV Connector: Ability to specify Column Delimiter in the Source dialog

For all the details, including a video demonstrating many of these updates, visit the [Power BI Blog](http://blogs.msdn.com/b/powerbi/archive/2015/12/16/more-power-bi-feature-updates-power-bi-desktop-december-update-and-new-power-bi-service-features.aspx).

**December 10, 2015**

* Pin report pages to dashboard

* Refresh dashboard tiles

* Use images in slicers

* Change interactions between report visuals

  For all the details, visit the [Power BI Blog](http://blogs.msdn.com/b/powerbi/archive/2015/12/10/power-bi-weekly-service-update-1210.aspx).


**December 8, 2015**

* [QR codes in Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/12/08/bridge-the-gap-between-your-physical-world-and-your-bi-using-qr-codes.aspx)

**December 3, 2015**

*  Automatically discover trends and uncover patterns in a dataset with Quick Insights: [video](http://blogs.msdn.com/b/powerbi/archive/2015/12/02/power-bi-updates-from-browser-to-desktop-and-new-automated-insights-mf.aspx) or  [article](powerbi-service-auto-insights.md)

* [Visualize your VMob data in Power BI](http://blogs.msdn.com/b/powerbi/archive/2015/11/25/visualize-your-vmob-data-in-power-bi.aspx)

*   [Power BI integration with Cortana](http://blogs.msdn.com/b/powerbi/archive/2015/12/01/announcing-power-bi-integration-with-cortana-and-new-ways-to-quickly-find-insights-in-your-data.aspx)

*   [Preview of Power BI gateway for enterprise](http://blogs.msdn.com/b/powerbi/archive/2015/12/02/announcing-preview-of-power-bi-gateway-for-enterprise-deployments.aspx)

* Introducting a new content pack: [Search Analytics from Bing on Power BI dashboards](http://blogs.msdn.com/b/powerbi/archive/2015/12/02/search-analytics-from-bing-on-your-power-bi-dashboards.aspx)

* New Developer-focused enhancements: [Two new APIs and easier app  registration](http://blogs.msdn.com/b/powerbi/archive/2015/12/02/power-bi-for-developers-reports-api-and-a-simple-app-registration-experience.aspx)


**November 24, 2015**

*   Pin Excel ranges to dashboards

*   Chromeless full screen mode for dashboards and reports

*   Know where your data is stored

* Improved loading of on-premises reports

* Share dashboards directly to another user's workspace

* Improved Google Analytics connector experience

* Close your power bi account

For all the details, visit the [Power BI Blog](http://blogs.msdn.com/b/powerbi/archive/2015/11/24/power-bi-weekly-service-update-1124.aspx)


**November 18, 2015**

*   Create a duplicate dashboard

*   Freely position dashboard tiles

*   Improved navigation for full screen view

* Better experience when inviting peers from your organization to Power BI groups

* Improved error messages for tiles

For all the details, visit the [Power BI Blog](http://blogs.msdn.com/b/powerbi/archive/2015/11/17/power-bi-weekly-service-update-1117.aspx)


**November 11, 2015**

*   New site for Power BI documentation, localized

*   Improved load time for reports

*   Update organizational content packs with report-only changes

* Power BI health status in Office 365 Admin Portal

* KPIs and images in tables, matrices, and cards

For all the details, visit the [Power BI Blog](http://blogs.msdn.com/b/powerbi/archive/2015/11/11/power-bi-weekly-service-update-1110.aspx)


**November 3, 2015**

*   Guided Power BI purchase experience.

*   Individuals can buy Power BI Pro.

*   Duplicate report page.

For all the details, visit the [Power BI Blog](http://blogs.msdn.com/b/powerbi/archive/2015/11/03/power-bi-weekly-service-update-1103.aspx)


**October 28, 2015**

- Share dashboards with Active Directory Security groups

- People picker

- Sharing with a large number of email addresses

- Collapse navigation pane through an URL parameterized

For all the details, visit the [Power BI Blog](http://blogs.msdn.com/b/powerbi/archive/2015/10/28/power-bi-weekly-service-update-1027.aspx)


**October 20, 2015**

-   Read-only members in Power BI groups

-   Featured questions in Q&A

-   Full screen pop-out mode for report visualizations

For all the details, visit the [Power BI blog](http://blogs.msdn.com/b/powerbi/archive/2015/10/20/power-bi-weekly-service-update-1020.aspx)


**October 13, 2015**

-   Full screen mode to display your dashboards and reports on big screen TVs

-   'Fit to screen’ support in full screen mode to display your entire dashboard in the available space

-   In-focus mode to get more details on dashboard tiles

-   Ability to view last update time for each tile

-   Ability to view the source for each tile

-   Planview Enterprise is an end-to-end portfolio and resource management solution that connects strategy to execution, improving decision-making across the enterprise. The Planview Enterprise content pack for Power BI allows you to visualize your resource and work management data in an entirely new way. Simply sign in with your credentials and begin to interactively explore your portfolio investment spend, budget status, and how well your projects align with strategic priorities.

View our [blog](http://blogs.msdn.com/b/powerbi/archive/2015/10/13/power-bi-weekly-service-update-1013.aspx) and [online documentation](powerbi-service-get-started.md) to learn more.


**October 6, 2015**

-   With Power BI Q&A, you can explore your data using simple, intuitive questions and receive answers in the form of interactive charts and graphs. With this release, we have added a feature to help you get started with Power BI Q&A, even when you do not know anything about the data. To get started with this, [navigate to any dashboard and click the “How to ask” link near the Q&A question box](powerbi-service-how-to-use-q-and-a.md). Power BI presents you with a number of suggestions based on your data.

-   Two weeks ago, we introduced support for inserting shapes into the report canvas in Power BI Desktop. This week, we are happy to announce that you can now add shapes to your report canvas when you are authoring and/or editing reports in the Power BI web app.

-   We have added the option to turn off email notification when you share a dashboard. Simply uncheck the “Send email notification to recipients” check box in the Power BI share dialog. You will be presented with a URL – copy and share this URL to your colleagues to give them access to the dashboard.

-   Microsoft Dynamics NAV is a business management solution for small to medium organizations. It offers customers a full solution for their business with greater control over their financials and business processes. The Power BI content pack provides out-of-box reports for Dynamics NAV users, such as sales and profit, opportunities pipeline, profitability and more. These metrics are organized on a dashboard that can be fully customized, allowing you to easily connect and immediately start exploring your data.

Check out the [blog](http://blogs.msdn.com/b/powerbi/archive/2015/10/06/power-bi-service-weekly-update-10-06.aspx) and [online documentation](powerbi-service-get-started.md) for more information.


**September 29, 2015**

-   With this week’s service update, when creating new reports you can now choose from multiple page sizes as well as define your own page size. This controls the size and aspect ratio of each page in the report.

-   We added additional visual formatting support for images and bubble charts. You can lock the aspect while resizing images to avoid image distortion and scatter chart bubbles can be configured to be filled or not.

-   Today, Power BI will send sharing invites to an alternate email address. When a dashboard is shared with you, we will send the sharing invite link both to your original email address and to your alternate email address (if you have it configured).

-   Power BI is available to all customers including those on the Dedicated on Multitenant (DonMT) O365 architecture. You will be using Power BI as a shared service in multi-tenant mode. In most cases, you can register for Power BI by following the simple [self-service-signup process](https://powerbi.microsoft.com/) – just enter your work email address, enter your name and password to get started. If you are the tenant administrator, you can assign licenses to your users using the instructions [here](http://go.microsoft.com/fwlink/?LinkId=627174).

-   Azure Audit Logs allows you to view control-plane operational logs in your Azure subscription. The Power BI Azure Audit Logs content pack can help you easily analyze and visualize the wealth of information contained in these logs. The content pack allows you to connect to your data and begin to discover insights with the out-of-the box dashboard and reports. Read our [blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/30/monitor-azure-audit-logs-with-power-bi.aspx) and [online documentation](powerbi-content-pack-azure-audit-logs.md)for more information.

[Learn more in our blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/30/power-bi-weekly-service-update-0929.aspx).


**September 22, 2015**

-   Have more flexibility on your dashboard to customize your dashboards with additional tile sizes, ranging from 1x1 to 5x5.

-   You can now [share (and un-share) a dashboard from your group space](powerbi-service-collaborate-with-your-power-bi-group.md) exactly the way you would do it in your own space. Once colleagues accept your sharing invitation, the shared dashboard (and their associated reports) will be added in their own space with read-only permission.

-   We added 5 additional [industry related samples](powerbi-sample-datasets.md) to Power BI: Customer Profitability, Human Resources, Opportunity Analysis, Procurement Analysis, and Sales and Marketing Sample.

-   Stripe is an advanced payment platform for online businesses. From start-ups to Fortune 500 companies, thousands of businesses use Stripe to accept payments in over 130 currencies, from anyone in the world. By connecting Power BI with your existing Stripe account, you’ll be able to [use the Power BI Stripe content pack to monitor, explore, and visualize your Stripe activity](powerbi-content-pack-stripe.md).

[Learn more in our blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/22/power-bi-weekly-service-update-0922.aspx).


**September 15, 2015**

-   You can now choose which dashboard you want to pin your visual to! You can choose the target dashboard from your existing dashboards, or even create a new dashboard and pin the visual to it in one shot.

-   Additionally, you can control your visual colors in the dashboard. If your report is using a different theme from the dashboard theme, you can control whether the visual retains current theme, or uses the default dashboard theme to achieve consistency across visuals from various sources.

-   You can now simply pin the tile from one dashboard to another, the same way you would pin a report visual to a dashboard.

-   If your 60-day Power BI Pro trial period is close to expiration, you can [contact us]( http://go.microsoft.com/fwlink/?LinkID=624573&clcid=0x409now) to request an extension to your trial. If approved, your trial will be extended for another 60 days.

-   comScore Digital Analytix is an online solution that provides insights into your user base through the best of analytics and audience demographics. With the Power BI comScore content pack, you can quickly connect and begin gaining insights into your web analytics data. This content pack includes an out-of-the box dashboard, a set of reports, and a curated data set to help you explore and drill into your data. Learn more about the content pack in our [blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/16/visualize-and-explore-your-comscore-data-with-power-bi.aspx) and [help topic](powerbi-content-pack-content-pack.md). 

**September 8, 2015**

-   ﻿Friendly Hyperlinks now allow you to provide links for your users without needing to display the entire URL in the textbox.

-   Drill Support has been added to Power BI Reports. You can create a Drill path that enables users to navigate from one level of data to related data.

-   Two new Industry Related Samples, It Spend Analysis and Supplier Quality Analysis, have been added under the samples section of the Get Data experience. These samples are great examples of how you can use your data to create insightful reports and dashboards.

-   We have a new content pack for tyGraph, which allows you to easily gain deeper insights into your Yammer data. The content pack includes a dashboard, a set of reports and a curated dataset to explore and provide insights such as the Measure of Active Engagement (The MAE Score) and content consumption metrics such as File Views and File Downloads. Learn more on our [blog](http://blogs.msdn.com/b/powerbi/archive/2015/09/09/analyze-and-monitor-your-tygraph-data-with-power-bi.aspx) and [help topic](powerbi-content-pack-tygraph.md).

**September 1, 2015**

-   Webtrends helps companies make sense of their customer data to drive digital marketing success. Users have the ability to observe, analyze and deliver insights on the visitor journey across web, social, mobile and SharePoint channels. With the release of [the Webtrends content pack](http://blogs.msdn.com/b/powerbi/archive/2015/09/01/visualize-and-explore-your-webtrends-data-in-power-bi.aspx), users will now have the ability to use Power BI to monitor, analyze, and visualize their Webtrends analytics data. The Webtrends content pack for Power BI [help page](powerbi-content-pack-webtrends.md) has more information.

-   Getting started with Q&A is even simpler. The moment you put your cursor inside the Q&A text box, we instantly display a list of questions and key metrics that are relevant to your data.  In the drop down, by default, you will see the questions for tiles already pinned to the dashboard as well as an entry for each table you have in your dataset.

-   The dynamic canvas size we display by default renders all our report items with optimal dimensions for the browser window size. If you want to lock in the aspect ratio, or want to fit your report in a different way, we now support another three options for you:Fit to Page, Fit to Width, and Actual Size.

-   We also Increased the limit on the number of datasets and reports you can have. You can now have up to 200 datasets and 200 reports for each dataset in your Power BI account.

**August 25, 2015**

-   Now you can use Power BI to monitor, explore and [visualize your Adobe Analytics data](http://blogs.msdn.com/b/powerbi/archive/2015/08/25/exploring-your-adobe-analytics-data-in-power-bi.aspx). With an out-of-box content pack, you can connect and discover insights from your data immediately. To learn more, visit the [Adobe Analytics content pack for Power BI help page](powerbi-content-pack-adobe-analytics.md).

**August 18, 2015**

-   Azure Mobile Engagement is an app analytics service that allows developers to track their application’s performance helping them increase retention and app usage. Using the [Power BI Azure Mobile Engagement content pack](http://blogs.msdn.com/b/powerbi/archive/2015/08/17/monitor-and-analyze-your-azure-mobile-engagement-data-in-power-bi.aspx) you can quickly connect to an out-of-box dashboard, a set of reports and a curated data set, and instantly get insights into how well your app is doing. Please see the [Azure Mobile Engagement content pack for Power BI help page](powerbi-content-pack-azure-mobile.md) for more information.

**August 11, 2015**

-   Mandrill is an email infrastructure service developed by MailChimp that lets you analyze your email campaigns from a wide variety of information. With the [Power BI Mandrill content pack](http://blogs.msdn.com/b/powerbi/archive/2015/08/12/explore-and-analyze-your-mandrill-data-in-power-bi.aspx), you can quickly connect to your Mandrill data and immediately gain insights into your newsletter or marketing campaign. For additional details on how to get started, please see the [Mandrill content pack for Power BI help page](powerbi-content-pack-mandrill.md).

**August 4, 2015**

-   Power BI now offers [Circuit ID](http://blogs.msdn.com/b/powerbi/archive/2015/08/04/circuit-id-data-with-power-bi.aspx) users the ability to track and monitor all their Circuit ID cloud communications services, empowering them to make the right business decisions. For additional details on how to get started, please see the Circuit ID content pack for [Power BI help page](powerbi-content-pack-circuit-id.md).

-   Today we’ve released an enhancement to the Share Dashboard feature to make it even easier to use.  If your organization uses Office 365 for email, you can now [share to an email distribution group](http://blogs.msdn.com/b/powerbi/archive/2015/08/04/easier-dashboard-sharing-with-distribution-groups.aspx) just the same way you would send an email in Outlook.  Just enter the address of the distribution group and click Share.  All members of the distribution group will receive an email invitation to view the dashboard.

**July 28, 2015**

-   We’re excited to announce that this week’s update to Power BI now offers database performance tracking with the [SQL Sentry content pack](http://blogs.msdn.com/b/powerbi/archive/2015/07/28/monitoring-your-sql-sentry-data-with-power-bi.aspx). This content pack includes a dashboard and reports that help you monitor the SQL Server deployments you track using the SQL Sentry Cloud. For additional details on how to get started, please see the SQL Sentry content pack for Power BI [help page](powerbi-content-pack-sql-sentry.md).

**July 24, 2015**

-   We're excited to announce our "general availability" (GA) release of Power BI. You can continue to use the free version of Power BI, or sign up for [Power BI Pro](powerbi-free-trial-for-power-bi-pro.md). As part of the GA release, we are offering some great new features:

-   A new visualization and report creation experience: The new reporting canvas has a larger selection of visualizations, more control over formatting of titles, legends, axes, colors, backgrounds, and more.

-   [Power BI groups](powerbi-service-create-a-group-in-power-bi.md): groups offer a powerful collaborative experience built on Office 365 groups.
-   [Organizational content packs](powerbi-service-organizational-content-packs-introduction.md): Power BI makes creating dashboards and reports extremely simple, and now users can publish this content to the organizational content gallery.

-   [Bring in whole Excel files](powerbi-bring-in-whole-excel-files.md): You can bring any Excel workbook stored on OneDrive for Business into Power BI and view the entire workbook, exactly as you would in Excel Online.

-   [Bring in CSV files](powerbi-service-get-data-from-files.md): Just like Excel or Power BI Desktop file, a comma-separated values text (CSV) file can also be a dataset for your Power BI dashboards and reports.

-   [Replace Excel, Power BI Desktop, and CSV files](powerbi-replace-an-excel-power-bi-desktop-or-csv-file.md): you can upload an updated version of a file to Power BI and it will replace the existing dataset. All the reports and dashboards that are connected to this dataset now automatically use the new version.

-   We’re excited to announce that this week’s update to Power BI now offers work item tracking in [the Visual Studio Online content pack](http://blogs.msdn.com/b/powerbi/archive/2015/07/22/monitoring-your-visual-studio-online-work-items-with-power-bi.aspx). This update includes a new dashboard, report and an updated data set offering insights on your work items in addition to important metrics about your Git repository, pull requests, and version control content included in the initial version. For additional details on how to get started, please see [the Visual Studio Online content pack for Power BI help page](powerbi-content-pack-quickbooks-online.md).

**July 14, 2015**

-   Acumatica Cloud ERP delivers a suite of fully integrated business management applications such as Financials, Distribution, CRM and Project Accounting, powered by a robust and flexible platform. With the Power BI [Acumatica content pack](http://blogs.msdn.com/b/powerbi/archive/2015/07/13/analyze-and-explore-your-acumatica-cloud-erp-data-with-power-bi.aspx), you can quickly connect and immediately gain insights into your opportunity data. This content includes an out-of-box dashboard, a set of reports and a curated dataset to explore and provide details such as your total won opportunities by date. Read more [here](powerbi-content-pack-acumatica.md). 

-   [Azure HDInsight](http://blogs.msdn.com/b/powerbi/archive/2015/07/14/visualize-big-data-with-power-bi-and-spark-for-azure-hdinsight.aspx) now offers a fully managed Spark service. This capability allows for scenarios such as iterative machine learning and interactive data analysis. Power BI allows you to directly connect to the data in Spark on HDInsight offering simple and live exploration. Read our [help doc](powerbi-spark-on-hdinsight-with-direct-connect.md) for more information.

-   [Office 365 navigation and application launcher integration](http://blogs.msdn.com/b/powerbi/archive/2015/07/15/new-capabilities-added-to-power-bi.aspx#launcher). With a single click, you can now navigate to all of your Office 365 applications.

-   [Specifying a custom URL](http://blogs.msdn.com/b/powerbi/archive/2015/07/15/new-capabilities-added-to-power-bi.aspx#url) that users navigate to when they click a tile. You now have the ability to control exactly where users go: a specific report, another dashboard, an SSRS report, or an external website. 

-   [Visibility and management of the storage](http://blogs.msdn.com/b/powerbi/archive/2015/07/15/new-capabilities-added-to-power-bi.aspx#storage) you are consuming in Power BI

-   [Configuring the visual and fields displayed in Q&A](http://blogs.msdn.com/b/powerbi/archive/2015/07/15/new-capabilities-added-to-power-bi.aspx#visual)

**July 7, 2015**

-   ﻿One of the most awaited and requested feature is now available in Power BI. Starting today, in Power BI you can [refresh datasets](http://blogs.msdn.com/b/powerbi/archive/2015/07/07/refresh-for-on-premises-sources-is-here.aspx) connecting to your on-premises sources such as SQL Server. You can refresh a dataset that has been created from a Power BI Designer file or an Excel workbook with data imported into the workbook using Power Query or Power Pivot. 

**June 30, 2015**

-   We released a new [Power BI UserVoice content pack](http://blogs.msdn.com/b/powerbi/archive/2015/07/01/monitor-and-visualize-your-uservoice-data-with-power-bi.aspx) that can help you monitor and visualize your UserVoice data and immediately gain insights into it with the ready-to-use dashboard and report.

**June 23, 2015**

-   Power BI Desktop files can be [refreshed](http://blogs.msdn.com/b/powerbi/archive/2015/06/22/announcing-refresh-support-for-power-bi-designer-files-in-the-power-bi-service.aspx) (scheduled refresh & refresh now) when uploaded to the Power BI service.

-   We are releasing the biggest visual change to Power BI since December: a cleaner and simpler experience to [Get Data](http://blogs.msdn.com/b/powerbi/archive/2015/06/23/the-new-get-data-experience.aspx).  When you click on Get Data, you are now presented a single screen with a set of categories to choose from. This will make it even easier to find the content that matters to you.

-   [Azure SQL Data Warehouse](http://blogs.msdn.com/b/powerbi/archive/2015/06/24/exploring-azure-sql-data-warehouse-with-power-bi.aspx) offers elastic scale and massive parallel processing. With the limited public preview announced today, Power BI allows you to directly connect to the data stored in your Azure SQL Data Warehouse offering simple and dynamic exploration. After creating a connection to your data warehouse, queries are generated in real time and sent back to the source as you explore the data. This removes the need to create and upload a custom data model and offers interactive exploration of your data.

**June 16, 2015**

-   SweetIQ lets you to easily track your local listings by providing location and review data from your local search ecosystem. Power BI allows you to analyze and monitor that data, by offering [out of box content](http://blogs.msdn.com/b/powerbi/archive/2015/06/16/analyze-and-monitor-your-sweetiq-data-with-power-bi.aspx) built from your SweetIQ data. For additional details on how to get started, please see the SweetIQ content pack for Power BI [help page](powerbi-content-pack-sweetiq.md).

**June 9, 2015**

-   Power BI allows you to monitor and explore that data using the [MailChimp APIs](http://blogs.msdn.com/b/powerbi/archive/2015/06/09/user-power-bi-to-monitor-and-visualize-your-mailchimp-data.aspx), offering a set of out-of-box content for your analytics. The dashboard, reports and dataset curated for the MailChimp scenario allow you to easily access data such as Top Campaigns of Total Opens by Day of Week. For additional details on how to get started, please see the MailChimp content pack for Power BI [documentation](powerbi-content-pack-mailchimp.md).

**June 2, 2015**

-   Now tracking important statistics about your apps is easy with Power BI and the [appFigures content pack](http://blogs.msdn.com/b/powerbi/archive/2015/06/02/explore-and-analyze-your-appfigures-data-with-power-bi.aspx). For additional details on how to connect and get started, see the [documentation](powerbi-content-pack-appfigures.md) for appFigures content pack for Power BI.

**May 28, 2015**

-   Get quick insights into your QuickBooks Online account data using our [content pack](http://blogs.msdn.com/b/powerbi/archive/2015/05/28/get-quick-insights-into-your-quickbooks-online-account-data.aspx). For additional details on how to connect and get started, see the QuickBooks Online content pack for Power BI [documentation](powerbi-content-pack-quickbooks-online.md).

**May 19, 2015**

-   With this update, you can now connect to [Twilio through our content pack](powerbi-content-pack-twilio.md)

-   The Power BI API has new additions! You can now [list all tables](http://docs.powerbi.apiary.io/#reference/datasets/tables-collection/list-all-tables) and [update an existing table schema](http://docs.powerbi.apiary.io/#reference/datasets/table/update-an-existing-tables-schema)

**May 13, 2015**

-   With the latest update to Power BI, you can connect to the data logged by **SQL Database Auditing** with a set of out of box reports and a customized dashboard.﻿ This content pack makes it easy to find suspicious events, unusual activity, and trends, based on a dataset that has been created for your reporting. Learn more in the [blog post](http://blogs.msdn.com/b/powerbi/archive/2015/05/14/monitor-your-azure-sql-database-auditing-activity-with-power-bi.aspx) and [documentation](powerbi-azure-sql-database-auditing-connector.md).

-   You can connect directly to data stored in your **Azure SQL Database**. We dynamically generate and send down queries to the source, allowing you to create interactive reports directly over your database. You can read the [blog post](http://blogs.msdn.com/b/powerbi/archive/2015/05/13/using-power-bi-to-visualize-and-explore-azure-sql-databases.aspx) and [documentation](powerbi-azure-sql-database-with-direct-connect.md) for more information.

**May 7, 2015**

-   You can now use the **Visual Studio Online** content pack for Power BI to gain insights into your git and TFVC team projects. You can read our [documentation](powerbi-content-pack-visual-studio-online.md) or [blog post](http://blogs.msdn.com/b/powerbi/archive/2015/05/07/gain-understanding-and-insights-into-projects-in-visual-studio-online-with-power-bi.aspx) for more information.

-   We updated our look to a new modern design, a look that is fresh and distinctive while keeping your focus on what matters: your data and your insights.

**April 28, 2015**

-   ﻿Power BI is now available in **44 languages**. Read our [blog post](http://blogs.msdn.com/b/powerbi/archive/2015/04/28/power-bi-preview-now-available-in-your-language.aspx) to see the full list.

**April 23, 2015**

-   You can now visualize and explore your **Microsoft Dynamics Marketing** data with our new content pack! You can read our [blog post](http://blogs.msdn.com/b/powerbi/archive/2015/04/23/monitor-and-explore-your-microsoft-dynamics-marketing-data-with-power-bi.aspx) and [documentation](powerbi-content-pack-microsoft-dynamics-marketing.md) for more information.﻿

**April 15, 2015**

-   You can now visualize and explore your **Google Analytics** data with our new content pack! With the Google Analytics content pack you will get a dashboard, report and dataset that allow you to gain insights into the usage of your site in the last 6 months. You can read [our blog post](http://blogs.msdn.com/b/powerbi/archive/2015/04/15/visualize-and-explore-your-google-analytics-data-with-power-bi.aspx) and [documentation](powerbi-content-pack-google-analytics.md) for more information.

-   You can now **pin all cards** expect those containing KPIs and Images from Q&A and reports

-   You can now **use cards in Q&A** by using the phrase 'as card' at the end of your query

**March 31, 2015**

-   **GitHub **dashboards have new visuals that focus on community building, improved calculations, and improved layout

-   **SendGrid **dashboards have new visuals and a new layout to help you find better insights

-   You can now use** treemaps in Q&A** by using the phrase 'as treemap' at the end of your query

-   You can now **pin treemaps** from Q&A and reports 

-   Lots of bug fixes!

**February 25, 2015**

-   Bug fixes and improvements to user experience and reliability. 

**January 26, 2015**

-   Service usability and reliability has been improved through various bug fixes. ﻿

**﻿December 11, 2014**

-   Reliability of refresh with OneDrive has been improved.  Some situations where workbooks were not refreshing from OneDrive have been resolved.

## See also  
[Get started with Power BI](powerbi-service-get-started.md)  
