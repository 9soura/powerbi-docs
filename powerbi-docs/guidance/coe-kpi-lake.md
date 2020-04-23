---
title: Microsoft's BI transformation
description: Learn how Microsoft successfully drives a data culture of business decision making with Power BI.
author: peter-myers
ms.reviewer: asaxton

ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2020
ms.author: v-pemyer
---
# Microsoft's BI transformation

This article targets IT professionals and IT managers. It describes how we at Microsoft strive to continuously modernize by using our data as an asset. And, it shares how we successfully drive a data culture of business decision making with Power BI.

Some background first: Today, the explosion of data is impacting consumers and businesses at breakneck speeds. Succeeding in this data-intensive environment requires smart analysts and savvy executives that are able to distill enormous amount of data into succinct insights. The revolutions in Microsoft's BI tools have revolutionized the way that Microsoft itself explores their data and gets to the right insights needed to drive impact in the company.

So, how can your organization, too, revolutionize the way it works with data? Let's help you understand by sharing the story of our BI transformation journey.

## Microsoft journey

Several years ago at Microsoft, our organizational culture encouraged individuals to pursue full ownership of data and insights. It also experienced strong cultural resistance to doing things in a standardized way. So, the organizational culture led to reporting and analytic challenges. Specifically, it led to:

- Inconsistent data definitions, hierarchies, metrics, and Key Performance Indicators (KPIs). For example, each division/company(?) had their own way of reporting on new revenue. There was no consistency, yet a lot of confusion.
- Analysts spending 75% of time collecting and compiling data.
- 78% of reports created in "offline environment".
- Over 350 centralized finance tools and systems.
- Approximately $30 million annual spend on "shadow applications".

These challenges prompted us to think about how we could do things better. Finance teams received executive support to transform the business review process for the FY16 mid-year review, which ultimately led to building the _Starlight_ platform and the _KPI Lake_. (We'll discuss more about our BI platform later.) Ultimately, these innovations then led to business reviews being transformed from dense tabular views into simpler, more insightful visuals focused on key business themes.

How did we achieve this successful outcome? In essence, by delivering centralized BI managed by IT and extending it with self-service BI (SSBI). We can describe it in two creative ways:  _discipline at the core_ and _flexibility at the edge_.

### Discipline at the core

Discipline at the core means that IT retains control by curating a single master data source. And, by delivering standardized corporate BI, and defining consistent taxonomies and hierarchies of KPIs. Importantly, data permissions are enforced centrally to ensure our people can only ever read the data they need.

First, we understood that our BI transformation wasn't a technology problem. To achieve success we learned to first define success, and then translate it into key metrics and data points. It cannot be understated how important it was for us to achieve consistency of definition across our data.

Our transformation didn't happen all at once. We prioritized the delivery of key subject areas and about 20-30 KPIs. Then, gradually over time, we expanded the number and depth of subject areas, and built out more complex hierarchies of KPIs. It allows us to roll up lower-level KPIs to higher ones. Today our total KPI count exceeds 2000, of which each is a key measure of success, and is aligned to corporate objectives. Now across the company, corporate reports and SSBI solutions present KPIs that are well defined, consistent, and secure.

### Flexibility at the edge

At the edge of the core, analysts become more agile. They now benefit from the ability to analyze data more quickly. More formally, this scenario is described as _managed self-service BI_. Managed SSBI is about mutual benefit for IT and analysts. Importantly, we experienced optimizations by driving standardization, knowledge, and reuse of our data and BI solutions. And, as a company we derived more value synergistically as we found the right balance between centralized BI and managed SSBI.

TODO: Bridging paragraph required?

### Starlight and the KPI Lake

**Starlight** is the name given to the data unification and analytics platform, which supports Finance, Sales, Marketing, and EG. Its  mission is to deliver a robust, shared, and scalable data platform. The platform was built entirely by Finance, and continues in operation today using the latest Microsoft products.

The **KPI Lake** isn't an Azure Data Lake. Rather, it's a Starlight-powered tabular model hosted in Azure IaaS using Microsoft SQL Server Analysis Services. The tabular model delivers data sourced from over 45 internal sources, and defines numerous hierarchies and KPIs. Its mission is to enable business performance reporting and analysis teams across Finance, Marketing, and Sales. It does so to obtain timely, accurate, and well performing insights through unified models from relevant sources.

When first deployed, it was an exciting time because the tabular model resulted in immediate and measurable benefits. The first version centralized C+E Finance and Marketing BI platforms. Then, over the past six years, it's been expanded to consolidate additional business insight solutions. Today, it continues to evolve, powering our global and commercial business reviews as well as standard reporting and SSBI. Its adoption has spiked 5X since its release—well beyond our initial expectations.

Here's a summary of key benefits:

- It powers the Subsidiary Scorecard, worldwide QBUs, and Finance, Marketing, Global Sales, and WCB reports and analytics.
- It supports self-service analytics, enabling analysts to discover insights hidden in data.
- It drives reporting and analytics for Incentive Compensation, Marketing and Operations analysis, Sales Performance Metrics, Senior Leadership meetings, and the annual planning process.
- It delivers automated and dynamic reporting and analytics from a _single source of truth_.

The **KPI Lake** is a great success story. It's often presented to customers to showcase an example of how to effectively use our latest technologies. Not surprisingly, it's highly resonant with many of our commercial customers.

### How it works

The Starlight platform manages the flow of data from acquisition, to processing, all the way to publication:

1. Robust and agile data integration takes place on a scheduled basis, consolidating data from over 100 disparate raw sources. Source data systems include relational databases, Azure Cosmos DB databases, and Azure Synapse databases. Subject areas include Finance, Marketing, Sales, and Engineering.
2. Once staged, the data is conformed and enriched using master data and business logic. It's then loaded to data warehouse tables. The tabular model is then refreshed.
3. Analysts across the company use Excel and Power BI to deliver insights and analytics from the tabular model. And, it enables business owners to champion metric definitions for their own business. When necessary, scaling is achieved using Azure IaaS with load balancing.

## Lessons learned

Sharing our BI transformation story has value lessons to share. It allowed us to understand that SSBI can empower analysts to design, customize, and maintain their own BI solutions—they can anchor decisions based on fact. Because without this ability, analysts are forced to rely entirely upon IT data and reports, or worse, go without.

We understand that SSBI isn't a complete solution, nor is it a replacement for centralized BI. Also, it's not about analysts working in isolation. Rather, it's about analysts working more closely with IT to share the BI workload. Yet, all the while, IT retains control and focus on delivering "discipline at the core".

### SSBI advantages

Analysts can:

- Access and work with corporate data without reliance on IT.
- Create ad hoc solutions.
- Create personal and team-centric solutions.
- Base decisions on data instead of intuition.
- Make faster and more accurate decisions.
- Define alerts to be notified of data changes.

### SSBI considerations

However, despite many advantages associated with SSBI, there are considerations that IT must be aware of:

- SSBI requires time and expense to implement and maintain.
- Analysts require training, tools, and permissions to access corporate data.
- Data catalogs need to be maintained to provide discoverable information describing corporate data.
- Inappropriate SSBI queries can negatively impact on corporate system performance and availability.
- SSBI solutions can result in duplication of effort, and duplication of data and logic. It's commonly referred to as _multiple versions of the truth_, or _spreadmart_ (when done in Excel).
- SSBI solutions may not be known to IT, documented, reviewed, approved, backed up, or adequately secured.
- Knowledge of—and expertise to maintain—SSBI solutions could be lost when an analyst leaves the organization.

### Managed SSBI

Managed BI is about mutual benefit for IT and analysts, and IT governance. The goal of clear IT governance is to ensure investments in IT generate business value and mitigate risk. Good governance should increase adoption of BI, and also ensure responsible BI by managing with oversight to:

- Review, approve, and audit SSBI solutions.
- Ensure trustworthy data is delivered in compliant, responsive, and secure ways.
- Ensure SSBI solutions remain available with current data, and are backed up.
- Have visibility into how data is used throughout the organization.
- Incorporate—or upgrade—SSBI solutions into centrally managed BI solutions, if appropriate.
- Scale compute resources to support demand, when required.
