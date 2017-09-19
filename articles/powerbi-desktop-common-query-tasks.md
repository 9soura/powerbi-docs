﻿<properties
   pageTitle="Common query tasks in Power BI Desktop"
   description="Common query tasks in Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
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
   ms.date="09/06/2017"
   ms.author="davidi"/>
# Common query tasks in Power BI Desktop

When working in the **Query Editor** window of Power BI Desktop, there are a handful of commonly used tasks. This document demonstrates those common tasks, and provides links for additional information. 

The common Query tasks demonstrated here are the following:

-    Connect to Data
-    Shape and Combine Data
-    Group Rows
-    Pivot Columns
-    Create Custom Columns
-    Query Formulas

We’ll use a few data connections to complete these tasks. The data is available for you to download or connect to, in case you want to step through these tasks yourself.

The first data connection is an Excel workbook. The other is a Web resource (which is also used in other Power BI Desktop help content) which can be accessed from here:

[*http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx*](http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

The steps necessary to connect to both of those data sources is where the common Query tasks begin.

## Connect to Data

To connect to data in Power BI Desktop, select the **Get Data** button from the **Home** tab on the ribbon. Power BI Desktop presents a menu with the most common data sources. For a complete list of data sources to which Power BI Desktop can connect, select the **More...** button at the bottom of the menu. For more information, see [Data Sources in Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471643).

![](media/powerbi-desktop-common-query-tasks/CommonQueryTasks_GetData.png)

To start with, select **Excel** and navigate to the workbook, then select it. Query inspects the workbook, then presents the data it found in the **Navigator** window.

![](media/powerbi-desktop-common-query-tasks/CommonQueryTasks_Navigator.png)

You can select **Edit** to adjust, or *shape,* the data before loading it into Power BI Desktop. Editing a query before loading is especially useful when working with large data sets that you intend to pare down before loading. We want to do that, so we select **Edit**.

Connecting to different types of data is just as easy. We also want to connect to a Web resource. Select **Get Data \> More...** and then select **Other \> Web**.

![](media/powerbi-desktop-common-query-tasks/CommonQueryTasks_GetData_Other.png)

The **From Web** window appears, where you can type in the URL of the Web page.

![](media/powerbi-desktop-common-query-tasks/DataSources_FromWebBox.png)

Select **OK**, and like before, Power BI Desktop inspects the workbook and presents the data it finds in the **Navigator** window.

Other data connections are similar. If authentication is required to make a data connection, Power BI Desktop prompts you for the appropriate credentials.

For a step-by-step demonstration of connecting to data in Power BI Desktop, see [Connect to Data in Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471635).

## Shape and Combine Data

You can easily shape and combine data with Query Editor. This section includes a few examples of how you can shape data. For a more complete demonstration of shaping and combining data, see **﻿**[Shape and Combine Data with Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471644).

In the previous section we connected to two sets of data – an Excel workbook, and a Web resource. Once loaded in Query Editor we see the following, with the query from the Web page selected (from the available queries listed in the **Queries** pane, on the left side of the Query Editor window).

![](media/powerbi-desktop-common-query-tasks/CommonQueryTasks_QueryPaneLoaded.png)

When you shape data, you transform a data source into the form and format that meets your needs. In this case, we don’t need that first column, titled *Header*, so we’ll remove it.

In **Query Editor**, many commands can be found in the ribbon, and in a context-sensitive right-click menu. For example, when I right-click on the *Header* column, the menu that appears lets me remove the column. I could also select the column and then select the **Remove Columns** button from the ribbon.

![](media/powerbi-desktop-common-query-tasks/CommonQueryTasks_RemoveColumns.png)

There are many other ways I could shape the data in this query; I could remove any number of rows from the top, or from the bottom; I could add columns, split columns, replace values, and perform other shaping tasks to direct Query Editor to get the data how I want it.

## Group Rows

In Query Editor, you can group the values in multiple rows into a single value. This can be useful when summarizing the number of products offered, the total sales, or the count of students.

In this example, we group rows in an education enrollment data set. The data is from an Excel workbook, and has been shaped in Query Editor to get just the columns we need, renamed the table, and performed a few other transforms.

Let’s find out how many Agencies (this includes school districts, and other education agencies such as regional service districts, and so on) each state has. We select the *State Abbr* column then select the **Group By** button in the **Transform** tab or the **Home** tab of the ribbon (**Group By** is available in both tabs).

![](media/powerbi-desktop-common-query-tasks/CommonQueryTasks_GroupBy.png)

The **Group By…** window appears. When Query Editor groups rows, it creates a new column into which it places the **Group By** results. You can adjust the **Group By** operation in the following ways:

1.  *Group by* – this is the column to be grouped; Query Editor chooses the selected column, but you can change that in this window to any column in the table.

2.  *New column name* – Query Editor suggests a name for the new column, based on the operation it applies to the column being grouped, but you can name the new column anything you want.

3.  *Operation* – here you specify the operation that Query Editor applies.

4.  *The +/- signs* – you can perform aggregation operations (**Group By** actions) on multiple columns, and perform multiple aggregations, all within the **Group By** window, and all in one operation. Query Editor creates a new column (based on your selections in this window) that operate on multiple columns. Select the **+** button to add more columns or aggregations to a **Group By** operation. You can remove a column or aggregation by selecting the – icon, so go ahead and try it, and see what it looks like. 

 ![](media/powerbi-desktop-common-query-tasks/CommonQueryTasks_GroupByNumbered.png)

When we select **OK**, Query performs the **Group By** operation, and returns the results. Whew, look at that – Ohio, Texas, Illinois, and California each have over a thousand agencies!

![](media/powerbi-desktop-common-query-tasks/CommonQueryTasks_GroupedResult.png)

And with Query Editor, you can always remove the last shaping operation by selecting the **X** next to the step just completed. So go ahead and experiment, redo the step if you don’t like the results, until Query Editor shapes your data just the way you want it.

## Pivot Columns

With Power BI Desktop, you can pivot columns, and create a table that contains aggregated values for each unique value in a column. For example, if you need to know how many different products you have in each product category, you can quickly create a table the does precisely that.

Let’s look at an example. The following **Products** table has been shaped to only show each unique product (by name), and which category each product falls under. To create a new table that shows a count of products for each category (based on the *CategoryName* column), select the column, then select **Pivot Column** from the **Transform** tab on the ribbon.

![](media/powerbi-desktop-common-query-tasks/PivotColumns_PivotButton.png)

The **Pivot Column** window appears, letting you know which column’s values will be used to create new columns (1), and when you expand **Advanced option** (2), you can select the function that will be applied to the aggregated values (3).

![](media/powerbi-desktop-common-query-tasks/PivotColumns_PivotDialog.png)

When you select **OK**, Query displays the table according to the transform instructions provided in the **Pivot Column** window.

![](media/powerbi-desktop-common-query-tasks/PivotColumns_PivotComplete.png)

## Create Custom Columns

In Query Editor you can create custom formulas that operate on multiple columns in your table, then place the results of such formulas into a new (custom) column. Query Editor makes it easy to create custom columns.

In Query Editor, select **Add Custom Column** from the **Add Column** tab on the ribbon.

![](media/powerbi-desktop-common-query-tasks/CommonQueryTasks_CustomColumn.png)

The following window appears. In the following example, we create a custom column called *Percent ELL* that calculates the percentage of total students that are English Language Learners (ELL).

![](media/powerbi-desktop-common-query-tasks/CustomColumn_AddCustomColumnDialog.png)

Like any other applied step in Query Editor, if the new custom column doesn’t provide the data you’re looking for, you can simply delete the step from the **Applied Steps** section of the **Query Settings** pane by selecting the **X** next to the **Added Custom** step.

![](media/powerbi-desktop-common-query-tasks/CustomColumn_AddedAppliedStep.png)

## Query Formulas

You can edit the steps that Query Editor generates, and you can create custom formulas to get precise control over connecting to and shaping your data. Whenever Query Editor performs an action on data, the formula associated with the action is displayed in the **Formula Bar**. To view the **Formula Bar**, select the checkbox next to **Formula Bar** in the **View** tab of the ribbon.

![](media/powerbi-desktop-common-query-tasks/QueryFormulas_FormulaBar.png)

Query Editor keeps all applied steps for each query as text that you can view or modify. You can view or modify the text for any query using the **Advanced Editor**, which is displayed when you select **Advanced Editor** from the **View** tab of the ribbon.

![](media/powerbi-desktop-common-query-tasks/QueryFormulas_AdvancedEditorButton.png)

Here's a look at the **Advanced Editor**, with the query steps associated with the **USA\_StudentEnrollment** query displayed. These steps are created in the Power Query Formula Language, often referred to as **M**. For information, see [Learn about Power Query formulas](https://support.office.com/article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f?ui=en-US&rs=en-US&ad=US). To view the language specification itself, download the [Microsoft Power Query for Excel Formula Language Specification](http://go.microsoft.com/fwlink/?linkid=320633).﻿

![](media/powerbi-desktop-common-query-tasks/QueryFormulas_AdvancedEditor.png)

Power BI Desktop provides an extensive set of formula categories. For more information, and a complete reference of all Query Editor formulas, visit [Power Query Formula Categories](https://support.office.com/en-in/article/Power-Query-formula-categories-125024ec-873c-47b9-bdfd-b437f8716819).

The formula categories for Query Editor are the following:

-   Number
    -   Constants
    -   Information
    -   Conversion and formatting
    -   Format
    -   Rounding
    -   Operations
    -   Random
    -   Trigonometry
    -   Bytes
-   Text
    -   Information
    -   Text comparisons
    -   Extraction
    -   Modification
    -   Membership
    -   Transformations
-   Logical
-   Date
-   Time
-   DateTime
-   DateTimeZone
-   Duration
-   Record
    -   Information
    -   Transformations
    -   Selection
    -   Serialization
-   List
    -   Information
    -   Selection
    -   Transformation
    -   Membership
    -   Set operations
    -   Ordering
    -   Averages
    -   Addition
    -   Numerics
    -   Generators
-   Table
    -   Table construction
    -   Conversions
    -   Information
    -   Row operations
    -   Column operations
    -   Membership
-   Values
-   Arithmetic operations
-   Parameter Types
-   Metadata
-   Accessing data
-   URI
-   Binary formats
    -   Reading numbers
-   Binary
-   Lines
-   Expression
-   Function
-   Error
-   Comparer
-   Splitter
-   Combiner
-   Replacer
-   Type

## More Information

There are all sorts of things you can do with Power BI Desktop. For more information on its capabilities, check out the following resources:

-   [Getting Started with Power BI Desktop](powerbi-desktop-getting-started.md)

-   [Query Overview with Power BI Desktop](powerbi-desktop-query-overview.md)

-   [Data Sources in Power BI Desktop](powerbi-desktop-data-sources.md)

-   [Connect to Data in Power BI Desktop](powerbi-desktop-connect-to-data.md)

-   [Shape and Combine Data with Power BI Desktop](powerbi-desktop-shape-and-combine-data.md)
