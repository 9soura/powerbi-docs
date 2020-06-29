---
title: BI solution architecture in the COE
description: Learn what to consider when designing and developing a robust BI platform.
author: peter-myers
ms.reviewer: asaxton

ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/29/2020
ms.author: v-pemyer
---
# BI solution architecture in the COE

This article targets IT professionals and IT managers. It provides a technical overview of our Business Intelligence (BI) solution architecture and highlights the different technologies employed. Technologies include Azure, Power BI, and Excel. Together they can be leveraged to deliver a scalable and data-driven cloud BI platform.

Designing a robust BI platform is somewhat like building a bridge; a bridge that connects transformed and enriched source data to data consumers. The design of such a complex structure requires an engineering mindset, though it can be one of the most creative and rewarding IT architectures you could design.

The platform must support specific demands. Specifically, it must scale and perform to meet the expectations of business services and data consumers. At the same time, it must be secure from the ground up. And, it must be sufficiently resilient to adapt to change, because it's a certainty that in time new data and subject areas must be brought online.

## Frameworks

At Microsoft, from the outset we adopted a systems-like approach by investing in framework development. Technical and business process frameworks increase the reuse of design and logic and provide a consistent outcome. They also offer flexibility in architecture leveraging many technologies, and they streamline and reduce engineering overhead via repeatable processes.

We learned that well-designed frameworks increase visibility into data lineage, impact analysis, business logic maintenance, managing taxonomy, and streamlining governance. Also, development became faster and collaboration across large teams became more responsive and effective.

We'll describe several of our frameworks in this article.

## Data models

Data models provide you with control over how data is structured and accessed. To business services and data consumers, data models are their interface to the BI platform.

A BI platform can deliver three different types of models:

- Enterprise models
- BI models
- Machine Learning (ML) models

### Enterprise models

**Enterprise models** are built and maintained by IT architects. They're sometimes referred to as dimensional models or data marts. Typically, data is stored in relational format as dimension and fact tables. They store cleansed and enriched data consolidated from many systems and they represent an authoritative source for reporting and analytics.

Enterprise models deliver a consistent and single source of data for reporting and BI. They're built once and shared as a corporate standard. Governance policies ensure data is secured, so access to sensitive data sets, such as customer information or financials, is restricted on a needs-basis. They adopt naming conventions ensuring consistency, thereby further establishing credibility of data and quality.

In a cloud BI platform, enterprise models can be deployed to a [Synapse SQL pool in Azure Synapse](/azure/synapse-analytics/sql-data-warehouse/sql-data-warehouse-overview-what-is#synapse-sql-pool-in-azure-synapse). The Synapse SQL pool then becomes the single version of truth the organization can count on for faster and more robust insights.

### BI models

**BI models** represent a semantic layer over enterprise models. They're built and maintained by BI developers and business users. BI developers create core BI models that source data from enterprise models. Business users can create smaller-scale, independent models—or, they can extend core BI models with departmental or external sources. BI models commonly focus on a single subject area, and are often widely shared.

Business capabilities are enabled not by data alone, but by BI models that describe concepts, relationships, rules, and standards. This way, they represent intuitive and easy-to-understand structures, which define data relationships and encapsulate business rules as calculations. They can also enforce fine-grained data permissions, ensuring the right people have access to the right data. Importantly, they accelerate query performance, providing extremely fast interactive analytics even over terabytes of data. Like enterprise models, BI models adopt naming conventions ensuring consistency.

In a cloud BI platform, BI developers can deploy BI models to [Azure Analysis Services](/azure/analysis-services/), or [Power BI Premium capacities](../admin/service-premium-what-is.md#dedicated-capacities). We recommend deploying to Power BI when it's used as your reporting and analytics layer. These products support different storage modes, allowing data model tables to cache their data or to use [DirectQuery](directquery-model-guidance.md), which in a technology that passes queries through to an underlying source. DirectQuery is an ideal storage mode when tables represent large data volumes or there's a need to deliver near-real time results to reports. The two storage modes can be combined: [Composite modeling](composite-model-guidance.md) allows a mix of storage modes in a single model.

For heavily queried models, [Azure Load Balancer](/azure/load-balancer/load-balancer-overview) can be used to evenly distribute the query load across model replicas. It also allows you to scale your applications and create highly available BI models.

<!-- For more information on BI models, see [BI modeling and processing in the COE](https://TODO/).-->

### ML models

[**ML models**](/windows/ai/windows-ml/what-is-a-machine-learning-model) are built and maintained by data scientists. They're mostly developed from raw sources in the data lake. They can be experimental, requiring a data engineer for production use.

Trained ML models can reveal patterns within your data. In many circumstances, those patterns can be used to make predictions, which can be used to enrich data. For example, purchasing behavior can be used to predict customer churn or segment customers to enable targeted analysis. Prediction results can be added to enterprise models to allow analysis by customer segment.

In a cloud BI platform, you can use [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-ml)to train, deploy, automate, manage, and track ML models.

## Data warehouse

Sitting at the heart of a BI platform is the data warehouse—it hosts your enterprise models. It's a source of sanctioned data—as a system of record and as a hub—serving enterprise models for reporting, BI, and data science.

Many business services, including line-of-business (LOB) applications, can consume data from the data warehouse as an authoritative, governed, source of enterprise knowledge.

At Microsoft, our data warehouse is hosted on [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction) (ADLS Gen2) and Azure Synapse Analytics.

- **ADLS Gen2** makes Azure Storage the foundation for building enterprise data lakes on Azure. It's designed to service multiple petabytes of information while sustaining hundreds of gigabits of throughput. And, it offers low-cost storage capacity and transactions. What's more, it's supports Hadoop compatible access, which allows you to manage and access data just as you would with a Hadoop Distributed File System (HDFS). In fact, [Azure HDInsight](/azure/hdinsight/), [Azure Databricks](/azure/azure-databricks/what-is-azure-databricks), and Azure Synapse Analytics can all access data stored in ADLS Gen2. So, in a BI platform, it's a good choice to store raw source data, semi-processed or staged data, and production-ready data. In fact, we use it to store all our business data.
- **Azure Synapse Analytics** is an analytics service that brings together enterprise data warehousing and Big Data analytics. It gives you the freedom to query data on your terms, using either serverless on-demand or provisioned resources—at scale. Synapse SQL, a component of Azure Synapse Analytics, supports complete T-SQL-based analytics, so it's ideal to host enterprise models, comprising your dimension and fact tables. Tables can be efficiently loaded from ADLS Gen2 using simply [Polybase T-SQL](/sql/relational-databases/polybase/polybase-guide) queries. You then have the power of [MPP](/azure/synapse-analytics/sql-data-warehouse/massively-parallel-processing-mpp-architecture#synapse-sql-mpp-architecture-components) to run high-performance analytics.

### Business Rules Engine framework

We developed a **Business Rules Engine** (BRE) framework that enables cataloging any business logic that can be implemented in the data warehouse layer. A BRE can mean many things, but in the context of a data warehouse, it's useful for creating calculated columns in relational tables. These calculated columns are usually represented as mathematical calculations or calculations using conditional statements.

The idea is to split business logic from core BI code: Traditionally, business rules are hard-coded into SQL stored procedures, so it can result in much effort to maintain them when business needs change. In a BRE, business rules are defined once and used multiple times when applied to different data warehouse entities. If calculation logic needs to change, it only needs to be updated in one place and not in numerous stored procedures. There's a side benefit, too: A BRE framework drives transparency and visibility into the implemented business logic, which can be exposed via a set of reports that create a self-updating document.

## Data sources

A data warehouse can consolidate data from practically any data source. It's mostly built over LOB data sources, which are commonly relational databases storing subject-specific data for sales, marketing, finance, etc. These databases can be cloud-hosted, or they can reside on-premises. Other data sources can be file-based, especially web logs or IOT data sourced from devices. What's more, data can be sourced from Software-as-a-Service (SaaS) vendors.

At Microsoft, some of our internal systems output operational data direct to ADLS Gen2 using raw file formats. In addition to our data lake, other source systems comprise relational LOB applications, Excel workbooks, other file-based sources, and Master Data Management (MDM) and custom data repositories. MDM repositories allow us to manage our master data to ensure authoritative, standardized, and validated versions of data.

## Data ingestion

On a periodic basis, and according to the rhythms of the business, data is ingested from source systems and loaded into the data warehouse. It could be once a day or more frequent. Data ingestion is concerned with extracting, transforming, and loading data. Or, perhaps the other way round: extracting, loading, and then transforming data. The difference is where the transformation takes place. Transformations can be used to cleanse, conform, integrate, and standardize data. For more information, see [Extract, transform, and load (ETL).](/azure/architecture/data-guide/relational-data/etl)

Ultimately, the goal is to load the right data into your enterprise model as quickly and efficiently as possible.

At Microsoft, we use [Azure Data Factory](/azure/data-factory/introduction) (ADF) to schedule and orchestrate data validations, transformations, and bulk loads from external source systems into our data lake. It's managed by custom frameworks that scale and process data in parallel. In addition, comprehensive logging is undertaken to support troubleshooting, performance monitoring, and to trigger alert notifications when certain conditions are met.

Meanwhile, Azure Databricks—an Apache Spark-based analytics platforms optimized for the Azure cloud services platform—performs transformations specifically for data science and also builds and executes ML models using Python notebooks. Scores from these ML models are loaded into the data warehouse, to integrate these insights with enterprise applications and reports. Because Azure Databricks accesses the data lake files directly, it eliminates or minimizes the need to copy or acquire data.

### Ingestion framework

We developed an **ingestion framework** as a set of configuration tables and procedures. It supports a data-driven approach to acquiring large volumes of data at high speed with minimal code. In short, this framework simplifies the process of data acquisition to load the data warehouse.

The framework depends on configuration tables that store data source and data destination-related information such as source type, server, database, schema, and table-related details. This design approach means that we don't need to develop specific ADF pipelines or SQL Server Integration Services (SSIS) packages. Instead, procedures can be written in the language of our choice to create ADF pipelines that are dynamically generated and executed at run time. So, data acquisition becomes a configuration exercise that's easily operationalized. Traditionally, it would require extensive development resources to create hard-coded ADF or SSIS packages.

This framework simplifies the process of handling upstream source schema changes, too: It's easy to update the configuration data—manually or automatically, when schema changes are detected—to acquire newly added attributes in the source system.

### Orchestration framework

We developed an **orchestration framework** to operationalize and orchestrate our data pipelines. It uses a data-driven design that depends on a set of configuration tables. These tables store metadata describing pipeline dependencies, and how to map source data to target data structures. The investment in developing such an adaptive framework has since paid for itself, because there's no longer a requirement to hard-code each data movement.

## Data storage

A data lake can be used to store raw data in high volume for later use, along with staging data transformations.

At Microsoft, we use ADLS Gen2 as our single source of truth to store raw data alongside with staged data, and production-ready data. It provides a highly scalable and cost-effective data lake solution for big data analytics. Combining the power of a high-performance file system with massive scale, it's optimized for data analytic workloads, accelerating time to insight.

ADLS Gen2 provides the best of two worlds: It's BLOB storage and a high-performance file system namespace, which we configure with fine grained access permissions.

Refined data is then stored in a relational database to provide high-performance, highly scalable data store for enterprise models, with security, governance, and manageability.

Subject-specific data marts are stored in Azure Synapse Analytics, which are loaded by Azure Databricks or Polybase T-SQL queries.

## Data consumption

At the reporting layer, business services can consume enterprise data sourced from the data warehouse, but it can also use data from the data lake for ad hoc analysis, or data science tasks.

Fine-grained permissions are enforced at all layers: In the data lake, in enterprise models, and in BI models. They ensure data consumers can only ever see the data they have permission to access.

At Microsoft, we use Power BI reports and dashboards, and Power BI paginated reports. Some reports and ad hoc analysis is done in Excel—particularly for financial reporting.

Data dictionaries, providing reference information about our data models, are made available to our users. Dictionaries document model designs, providing descriptions about entities, formats, structure, data lineage, relationships, and calculations. We use [Azure Data Catalog](/azure/data-catalog/overview) to make our data sources easily discoverable and understandable.

Typically, data consumption patterns differ based on role:

- **Data analysts** connect directly to core BI models. When core BI models contain all data and logic they need, they can use live connections to create Power BI reports and dashboards. When they need to extend the models with departmental data, they can create Power BI [composite models](composite-model-guidance.md). If there's a need for spreadsheet-style reports, they can use Excel to produce reports based on core BI models or departmental BI models.
- **BI developers** and operational report authors connect directly to the enterprise models. They can use Power BI Desktop to create live connection analytic reports. They can also author operational-type BI reports as Power BI paginated reports, writing native SQL queries to access data from the Azure Synapse Analytics enterprise models by using T-SQL, or Power BI models by using DAX or MDX.
- **Data scientists** connect directly to data in the data lake. They can use Azure Databricks and Python notebooks to develop ML models, which are often experimental and require specialty skills for production use.

## Governance and compliance

## Next steps

For more information about this article, check out the following resources:

- [Enterprise BI in Azure with Azure Synapse Analytics](/azure/architecture/reference-architectures/data/enterprise-bi-synapse)
<!--- [BI modeling and processing in the COE](https://TODO/)-->
- Questions? [Try asking the Power BI Community](https://community.powerbi.com/)
- Suggestions? [Contribute ideas to improve Power BI](https://ideas.powerbi.com/)
