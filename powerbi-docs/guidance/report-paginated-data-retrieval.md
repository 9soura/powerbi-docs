---
title: Data retrieval guidance for paginated reports
description: Guidance for creating data sources and datasets for Power BI paginated reports.
author: peter-myers
ms.reviewer: asaxton

ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 02/16/2020
ms.author: v-pemyer
---

# Data retrieval guidance for paginated reports

This article targets you as a report author designing Power BI [paginated reports](../paginated-reports-report-builder-power-bi.md). It provides recommendations to help you define optimal report data sources and datasets.

## Data source types

Paginated reports natively support both relational and analytic data sources. These sources are further categorized, as either cloud-based or on-premises. On-premises data sources—whether hosted on-premises, or in a virtual machine—require a data gateway so Power BI can connect. Cloud-based means that Power BI can connect directly using an Internet connection.

If you can choose the data source type (possibly the case in a new project), we recommend that you use cloud-based data sources. Paginated reports can connect with lower network latency, especially when the data sources reside in the same region as your Power BI tenant. Also, it's possible to connect to these sources by using Single Sign-On (SSO). It means the report consumer's identity can flow to the data source, allowing per-user row-level permissions to be enforced. Currently, SSO isn't supported for on-premises data sources (meaning SQL Server Analysis Services cannot enforce per-user row-level permissions).

### Relational data sources

Generally, relational data sources are well suited to operational style reports, like sales invoices. They're also suited for reports that need to retrieve very large datasets (in excess of 10,000 rows). Relational data sources can also define stored procedures, which can be executed by report datasets. Stored procedures deliver several benefits:

- Parameterization
- Encapsulation of programming logic, allowing for more complex data preparation
- Improved maintainability, allowing stored procedure logic to be easily updated. In some cases, it can be done without the need to modify and republish paginated reports (providing column names and data types remain unchanged).
- Better performance, as their execution plans are cached for reuse
- Reuse of stored procedures across multiple reports

> [!NOTE]
> In some instances, on-premises stored procedure executions may fail. For more information and a design workaround, see [On-premises stored procedure execution for paginated reports](report-paginated-onpremises-stored-procedure.md).

In Power BI Report Builder, you can use the relational query designer to graphically construct a query statement—but only for Microsoft data sources.

### Analytic data sources

Analytic data sources are well suited to both operational and analytic reports, and can deliver fast summarized query results even over very large data volumes. Model measures and KPIs can encapsulate complex business rules to achieve summarization of data. These data sources, however, are not suited to reports that need to retrieve very large datasets (in excess of 10,000 rows).

In Power BI Report Builder, you have a choice of two query designers: The Analysis Services DAX query designer, and the Analysis Services MDX query designer. These designers can be used for Power BI dataset data sources, or any SQL Server Analysis Services or Azure Analysis Services model—tabular or multidimensional.

We suggest you use the DAX query designer—providing it entirely meets your query needs. If the model doesn't define the measures you need, you will need to switch to query mode. In this mode, you can customize the query statement by adding expressions (to achieve summarization).

The MDX query designer requires your model to include measures. The designer has two capabilities not supported by the DAX query designer. Specifically, it allows you to:

- Define query-level calculated members (in MDX).
- Configure data regions to request [server aggregates](/sql/reporting-services/report-design/report-builder-functions-aggregate-function) in non-detail groups. If your report needs to present summaries of semi- or non-additive measures (like time intelligence calculations, or distinct counts), it will likely be more efficient to use server aggregates than to retrieve low-level detail rows and have the report compute summarizations.

## Query result size

In general, it's best practice to retrieve only the data required by your report. So, don't retrieve columns or rows that aren't required by the report.

To limit rows, you should always apply the most restrictive filters, and define aggregate queries. Aggregate queries group and summarize source data to retrieve higher-grain results. For example, consider that your report needs to present a summary salesperson sales. Instead of retrieving all sales order rows, create a dataset query that groups by salesperson, and summarizes sales for each group.

## Expression-based fields

It's possible to extend a report dataset with a field based on an expression. For example, when your dataset sources customer first name and last name, you might want a field that concatenates the two fields to produce the customer full name. To achieve this calculation, you have two options. You can:

- Create a _calculated field_, which is a dataset field based on an expression.
- Inject an expression directly into the dataset query (using the native language of your data source), which results in a regular dataset field.

We recommend the latter option, whenever possible. There are two good reasons why injecting expressions directly into your dataset query is better:

- It's possible your data source is optimized to evaluate the expression more efficiently than Power BI (it's especially the case for relational databases).
- Report performance is improved because there's no need for Power BI to materialize calculated fields prior to report rendering. Calculated fields can noticeably extend report render time when datasets retrieve a large number of rows.

## Field names

When you create a dataset, its fields are automatically named after the query columns. It's possible these names aren't friendly or intuitive. It's also possible that source query column names contain characters prohibited in Report Definition Language (RDL) object identifiers (like spaces and symbols). In this case, the prohibited characters are replaced with an underscore character (_).

We recommend that you first verify that all field names are friendly, concise, yet still meaningful. If not, we suggest you rename them _before_ you commence the report layout. It's because renamed fields don't ripple changes through to the expressions used in your report layout. If you do decide to rename fields after you've commenced the report layout, you will need to update any broken expressions.

## Filter vs parameter

It's likely that your paginated report designs will have report parameters. Report parameters are commonly used to prompt your report consumer to filter the report. As a paginated report author, you have two ways to achieve report filtering. You can map a report parameter to:

- A dataset _filter_, in which case the report parameter value(s) are used to filter the data already retrieved by the dataset.
- A dataset _parameter_, in which case the report parameter value(s) are injected into the native query sent to the data source.

> [!NOTE]
> All report datasets are cached on a _per-session basis_ for up to 10 minutes _beyond their last use_. A dataset can be re-used when submitting new parameter values (filtering), rendering the report in a different format, or interacting with the report design in some way, like toggling visibility, or sorting.

Consider, then, an example of a sales report that has a single report parameter to filter the report by a single year. The dataset retrieves sales for _all years_. It does so because the report parameter maps to the dataset filters. The report displays data for the requested year, which is subset of the dataset data. When the report consumer changes the report parameter to a different year—and then views the report—Power BI doesn't need to retrieve any source data. Instead, it applies a different filter to the already-cached dataset. Once the dataset is cached, filtering can be very fast.

Now, consider a different report design. This time the report design maps the sales year report parameter to a dataset parameter. This way, Power BI injects the year value into the native query, and the dataset retrieves data only for that year. Each time the report consumer changes the year report parameter value—and then views the report—the dataset retrieves a new query result for just that year.

Both design approaches can filter report data, and both designs can work well for your report designs. An optimized design, however, will depend on the anticipated volumes of data, data volatility, and the anticipated behaviors of your report consumers.

We recommend _dataset filtering_ when you anticipate a different subset of the dataset rows will be reused many times (thereby saving rendering time because new data doesn't need to be retrieved). In this scenario, you recognize that the cost of retrieving a larger dataset can be traded off against the number of times it will be reused. So, it's helpful for queries that are time consuming to generate. But take care—caching large datasets on a per-user basis may negatively impact on performance, and capacity throughput.

We recommend _dataset parameterization_ when you anticipate it's unlikely that a different subset of dataset rows will be requested—or, when the number of the dataset rows to be filtered is likely to be very large (and inefficient to cache). This design approach work well, too, when your data store is volatile. In this case, each report parameter value change will result in the retrieval of up-to-date data.

## Non-native data sources

If you need to develop paginated reports based on data sources that aren't [natively supported by paginated reports](../paginated-reports-data-sources.md), you can first develop a Power BI Desktop data model. This way, you connect to over 100 [Power BI data sources](../power-bi-data-sources.md). Once published to the Power BI service, you can then develop a paginated report to connect to the Power BI dataset.

## Data integration

If you need to combine data from multiple data sources, you have two options:

- **Combine report datasets**: If the data sources are [natively supported by paginated reports](../paginated-reports-data-sources.md), you can consider creating calculated fields that use the [Lookup](/sql/reporting-services/report-design/report-builder-functions-lookup-function) or [LookupSet](/sql/reporting-services/report-design/report-builder-functions-lookupset-function) Report Builder functions.
- **Develop a Power BI Desktop model**: It's likely more efficient, however, that you develop a data model in Power BI Desktop. You can use Power Query to combine queries based on any [supported data source](../power-bi-data-sources.md). Once published to the Power BI service, you can then develop a paginated report to connect to the Power BI dataset.

## Data-related images

Images can be used to add logos or pictures to your report layout. When images relate to the rows retrieved by a report dataset, you have two options:

- It's possible that image data can also be retrieved (if already stored in your database).
- When the images are stored on a web server, you can use a dynamic expression to create the image URL path.

For more information and suggestions, see [Image guidance for paginated reports](report-paginated-image.md).

## Unused datasets

When a report is run, all datasets are evaluated—even if they're not bound to report objects. For this reason, be sure to remove any test or development datasets before you publish the report to Power BI. They will place unnecessarily burden on your data sources, and consume capacity resources.

## Next steps

For more information related to this article, check out the following resources:

- [Supported data sources for Power BI paginated reports](../paginated-reports-data-sources.md)
- Questions? [Try asking the Power BI Community](https://community.powerbi.com/)
- Suggestions? [Contribute ideas to improve Power BI](https://ideas.powerbi.com/)
