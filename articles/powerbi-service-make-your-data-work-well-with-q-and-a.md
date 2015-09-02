<properties pageTitle="Make your data work well with Q&A in Power BI" description="Make your data work well with Q&A in Power BI" services="powerbi" documentationCenter="" authors="v-anpasi" manager="mblythe" editor=""/>
<tags ms.service="powerbi" ms.devlang="NA" ms.topic="article" ms.tgt_pltfrm="NA" ms.workload="powerbi" ms.date="06/26/2015" ms.author="v-anpasi"/>
# Make your data work well with Q&A in Power BI
[← Q&A in Power BI](https://support.powerbi.com/knowledgebase/topics/70394-q-a-in-power-bi)

In Power BI, Q&A can search structured data and choose the right visualization for your question -- that's what makes it a compelling tool to use.   

<p><spam><iframe width="500" height="281" src="https://www.youtube.com/embed/3z8e7KQqPP8" frameborder="0" allowfullscreen></iframe></span></p>

Q&A can work on any uploaded Excel file, but the more optimizations and data cleaning you do, the more robust Q&A performance is. 

## How Q&A works
Q&A has a set of core natural language understanding abilities that work across your data. It has context-dependent keyword search for your Excel table, column, and calculated field names. Second, it has built-in knowledge for how to filter, sort, aggregate, group, and display data. 

For example, in an Excel table named “Sales”, with columns “Product”, “Month”, “Units Sold”, “Gross Sales”, and “Profit”, you could ask questions about any of those entities.  You could ask to show sales, total profit by month, sort products by units sold, and many others. Read more about the [kinds of questions you can ask](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-1.aspx), and [asking questions using a question template](http://support.powerbi.com/knowledgebase/articles/474566) and [visualization types you can specify in a Q&A query](http://support.powerbi.com/knowledgebase/articles/469552).

## Prepare a workbook for Q&A

Q&A relies on the names of tables, columns, and calculated fields to answer data-specific questions, meaning what you call entities in your workbook is important!

Here are some tips for making the most of Q&A in your workbook.

-   Make sure your data is in an Excel table. Here's [how to create an Excel table](https://support.office.com/en-us/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US).
-   Make sure the names of your tables, columns, and calculated field make sense in English.
    For example, if you have a table with sales data, call the table “Sales”. Column names like “Year”, “Product”, “Sales Rep”, and “Amount” will work well with Q&A.

NOTE: If your workbook has a Power Pivot data model, you can do even more optimizations. Read more about [Demystifying Power BI Q&A part 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) from our in-house team of natural language experts.

## See Also:
[Q&A in Power BI](http://support.powerbi.com/knowledgebase/articles/474566-q-a-in-power-bi)  
[Tutorial: Introduction to Power BI Q&A](https://support.powerbi.com/knowledgebase/articles/607113)  
[Ask the right questions of Salesforce data in Power BI](http://support.powerbi.com/knowledgebase/articles/475138)  
[Get Data: Salesforce](http://support.powerbi.com/knowledgebase/articles/424863-get-data-salesforce-data)  
[Get data (for Power BI)](http://support.powerbi.com/knowledgebase/articles/434354-get-data)  
[Power BI - Basic Concepts](http://support.powerbi.com/knowledgebase/articles/487029-power-bi-preview-basic-concepts)