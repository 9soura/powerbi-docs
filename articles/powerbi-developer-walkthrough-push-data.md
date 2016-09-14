<properties
   pageTitle="Push data into a dashboard"
   description="Push data into a Power BI dashboard"
   services="powerbi"
   documentationCenter=""
   authors="mgblythe"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="04/15/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="mblythe"/>

# Push data into a Power BI dashboard

With the Power BI API, you can push data into a Power BI dashboard. For example, you want to extend an existing business workflow to push key data into your dashboard. In this case, you want to push a Sales Marketing dataset which has a Product table into a dashboard.

Before you get started pushing data into a dashboard, you need an Azure Active Directory (Azure AD) and a [Power BI account](powerbi-admin-free-with-custom-azure-directory.md).

To learn how to push a dataset into a dashboard, follow these steps. In the example, you push a Sales Marketing dataset with a Product table into a dashboard.

## Steps to push a dataset into a dashboard

- Step 1: [Register an app with Azure AD](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)
- Step 2: [Get an authentication access token](powerbi-developer-walkthrough-push-data-get-token.md)
- Step 3: [Create a dataset in a Power BI dashboard](powerbi-developer-walkthrough-push-data-create-dataset.md)
- Step 4: [Get a dataset to add rows into a Power BI table](powerbi-developer-walkthrough-push-data-get-datasets.md)
- Step 5: [Add rows to a Power BI table](powerbi-developer-walkthrough-push-data-add-rows.md)

The next section is a general discussion of Power BI API operations that push data.

## Power BI API operations to push data

With the Power BI REST API, you can push data sources to Power BI. When an app adds rows to a dataset, tiles on the dashboard are updated automatically with the updated data. To push data, you use the [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx) operation along with the [Add Rows](https://msdn.microsoft.com/library/mt203561.aspx) operation. To find a dataset, you use the [Get Datasets](https://msdn.microsoft.com/library/mt203567.aspx) operation. For any of these operations, you can pass a group id to work with a group. Use the [Get Groups](https://msdn.microsoft.com/library/mt243842.aspx) operation to get a list of group id's.

Here are the operations to push data into a dashboard:

- [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx)
- [Get Datasets](https://msdn.microsoft.com/library/mt203567.aspx)
- [Add Rows](https://msdn.microsoft.com/library/mt203561.aspx)
- [Get Groups](https://msdn.microsoft.com/library/mt243842.aspx)

You create a dataset in Power BI by passing a JavaScript Object Notation (JSON) string to the Power BI service. To learn more about JSON, see [Introducing JSON](http://json.org/).

The JSON string for a dataset has the following format:

**Power BI Dataset JSON object**

	{"name": "dataset_name", "tables":
	    [{"name": "", "columns":
	        [{ "name": "column_name1", "dataType": "data_type"},
	         { "name": "column_name2", "dataType": "data_type"},
	         { ... }
	        ]
	      }
	    ]
	}

So, for our Sales Marketing dataset example, you would pass a JSON string such as the example below. In this example, **SalesMarketing** is the name of the dataset, and **Product** is the name of the table. After you define the table, you define the table schema. For the **SalesMarketing** dataset, the table schema has these columns: ProductID, Manufacturer, Category, Segment, Product, and IsCompete.

**Example dataset object JSON**

	{
	    "name": "SalesMarketing",
	    "tables": [
	        {
	            "name": "Product",
	            "columns": [
	            {
	                "name": "ProductID",
	                "dataType": "int"
	            },
	            {
	                "name": "Manufacturer",
	                "dataType": "string"
	            },
	            {
	                "name": "Category",
	                "dataType": "string"
	            },
	            {
	                "name": "Segment",
	                "dataType": "string"
	            },
	            {
	                "name": "Product",
	                "dataType": "string"
	            },
	            {
	                "name": "IsCompete",
	                "dataType": "bool"
	            }
	            ]
	        }
	    ]
	}

For a Power BI table schema, you can use the following data types.

## Power BI table data types

|**Data type**|**Restrictions**
|---|---
|Int64|Int64.MaxValue and Int64.MinValue not allowed.
|Double|Double.MaxValue and Double.MinValue values not allowed. NaN not supported.+Infinity and -Infinity not supported in some functions (e.g. Min, Max).
|Boolean|None
|Datetime|During data loading we quantize values with day fractions to whole multiples of 1/300 seconds (3.33ms).
|String|Currently allows up to 128K characters.


## Learn more about pushing data into Power BI

To get started pushing data into a dashboard, see [Step 1: Register an app with Azure AD](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md) in the left navigation pane.

[Next Step >](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)

## See also
- [Sign up for Power BI](powerbi-admin-free-with-custom-azure-directory.md)
- [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx)
- [Get Datasets](https://msdn.microsoft.com/library/mt203567.aspx)
- [Add Rows](https://msdn.microsoft.com/library/mt203561.aspx)
- [Get Groups](https://msdn.microsoft.com/library/mt243842.aspx)
- [Introducing JSON](http://json.org/)
- [Overview of Power BI REST API](powerbi-developer-overview-of-power-bi-rest-api.md)
