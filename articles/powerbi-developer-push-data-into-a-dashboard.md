<properties
   pageTitle="Push data into a Power BI Dashboard"
   description="Push data into a Power BI Dashboard"
   services="powerbi"
   documentationCenter=""
   authors="dvana"
   manager="mblythe"
   editor=""
   tags=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="02/14/2016"
   ms.author="derrickv"/>


# Push data into a Power BI Dashboard

With the Power BI REST API, you can push data into a Power BI dashboard. For example, you want to extend an existing business workflow to push key data into your dashboard. In this case, you want to push a Sales Marketing dataset which has a Product table. To learn how to push a dataset, such as a Product table, into a dashboard, follow the steps in the left navigation page or go to [Walkthrough to push data into a Power BI dashboard](powerbi-developer-push-step-1.md).

The next section is a general discussion of Power BI API operations that push data.

## Power BI API operations to push data

With the Power BI REST API, you can push data sources to Power BI. When an app adds rows to a dataset, tiles on the dashboard are updated automatically with the updated data. To push data, you use the **Create Dataset** operation along with the **Add Rows** operation. To find out if a dataset exists, you use the **Get Datasets** operation. For any of these operations, you can pass a group id to work with a group. Use the **Get Groups** operation to get a list of group id's.

For more details about each operation, see the MSDN reference:

- [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx)
- [Add Rows](https://msdn.microsoft.com/library/mt203561.aspx)
- [Get Datasets](https://msdn.microsoft.com/library/mt203567.aspx)
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

So, for our Product example, you would pass a JSON string such as the example below. In this example, **SalesMarketing** is the name of the dataset, and **Product** is the name of the table. After you define the table, you define the table schema. For the **SalesMarketing** dataset, the table schema has these columns: ProductID, Manufacturer, Category, Segment, Product, and IsCompete.

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

For a Power BI table schema, you can use the following data types:

|Data type|Restrictions
|---|---
|Int64|Int64.MaxValue and Int64.MinValue not allowed.
|Double|Double.MaxValue and Double.MinValue values not allowed. NaN not supported.+Infinity and -Infinity not supported in some functions (e.g. Min, Max).
|Boolean|None
|Datetime|During data loading we quantize values with day fractions to whole multiples of 1/300 seconds (3.33ms).
|String|Currently allows up to 128K characters.

To learn more about how to create a dataset, see the [first step under Push data into a Power BI Dashboard](powerbi-developer-push-step-1.md) in the left navigation pane.

## Learn more about pushing data into Power BI

- [Walkthrough to push data into a Power BI dashboard](powerbi-developer-push-step-1.md)

## See also
- [Create Dataset](https://msdn.microsoft.com/library/mt203562.aspx)
- [Add Rows](https://msdn.microsoft.com/library/mt203561.aspx)
- [Get Datasets](https://msdn.microsoft.com/library/mt203567.aspx)
- [Get Groups](https://msdn.microsoft.com/library/mt243842.aspx)
- [Introducing JSON](http://json.org/)
