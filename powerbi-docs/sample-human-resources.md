---
title: 'Human Resources sample: Take a tour'
description: 'Human Resources sample for Power BI: Take a tour'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac

ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/14/2019
ms.author: maggies

LocalizationGroup: Samples
---
# Human Resources sample for Power BI: Take a tour

## Overview of the Human Resources sample
The Human Resources Sample content pack contains a dashboard, report, and dataset for a human resources department. In this sample, the human resources department has the same reporting model across different companies, even when they differ by industry or size. This sample looks at new hires, active employees, and employees who have left. It strives to uncover any trends in the hiring strategy. Our main objectives are to understand:

* Who we hire
* Biases in our hiring strategy
* Trends in voluntary separations

![Dashboard for the Human Resources sample](media/sample-human-resources/hr1.png)

This sample is part of a series that shows how you can use Power BI with business-oriented data, reports, and dashboards. This sample was created with real data by [obviEnce](http://www.obvience.com/), which has been anonymized. The data is available in several formats: content pack/app, Excel workbook, or .pbix Power BI Desktop file. See [Samples for Power BI](sample-datasets.md). This tutorial uses the Power BI service and the Human Resources Sample content pack. Because the report experiences are so similar, you can also follow along by using Power BI Desktop and the sample .pbix file. 

## Prerequisites

Before you can use the sample, you must first download it as a [content pack](#get-the-content-pack-for-this-sample), [pbix file](#get-the-pbix-file-for-this-sample), or 
[Excel workbook](#get-the-excel-workbook-for-this-sample).

### Get the content pack for this sample

1. Open the Power BI service (app.powerbi.com), sign in, and open the workspace where you want to save the sample.

2. In the bottom-left corner, select **Get Data**.
   
    ![Get data](media/sample-datasets/power-bi-get-data.png)
3. On the **Get Data** page that appears, select **Samples**.
   
4. Select **Human Resources Sample**, then choose **Connect**.  
   
   ![Get Data](media/sample-human-resources/pbi_hr_sample_connect.png)

5. Power BI imports the content pack and then adds a new dashboard, report, and dataset to your current workspace.
   
   ![Human Resources Sample entry](media/sample-human-resources/hr-sample-entry.png)
  
### Get the .pbix file for this sample

Alternatively, you can download the [Human Resources sample](http://download.microsoft.com/download/6/9/5/69503155-05A5-483E-829A-F7B5F3DD5D27/Human%20Resources%20Sample%20PBIX.pbix) as a .pbix file, which is designed for use with Power BI Desktop.

### Get the Excel workbook for this sample

If you want to view the data source for this sample, it's also available as an [Excel workbook](http://go.microsoft.com/fwlink/?LinkId=529780). The workbook contains Power View sheets that you can view and modify. To see the raw data, enable the Data Analysis add-ins, then select **Power Pivot > Manage**. To enable the Power View and Power Pivot add-ins, see [Take a look at the Excel samples from inside Excel itself](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself) for details.

## New hires
Let’s explore new hires first.

1. In your workspace, select the **Dashboards** tab, and open the **Human Resources Sample** dashboard.
2. On the dashboard, select the **New Hire Count, New Hires Same Period Last Year, Actives YoY % Change By Month** tile.  

   ![New Hire Count tile](media/sample-human-resources/hr2.png)  

   The Human Resources Sample report opens to the **New Hires** page.  

   ![New Hires page](media/sample-human-resources/hr3.png)

Items of interest:

* The **New Hire Count, New Hires SPLY and Actives YoY % Change by Month** combo chart shows we hired more people every month this year compared to last year. Significantly more people in some months.
* In the combo chart **New Hire Count and Active Employee Count by Region and Ethnicity**, notice we’re hiring fewer people in the **East** region.
* The **New Hires YoY Var by Age Group** waterfall chart shows we’re hiring mainly younger people. This trend may be due to the mostly part-time nature of the jobs.
* The **New Hire Count by Gender** pie chart shows a roughly even split.

Can you find more insights; for example, a region where the gender split is not even? Select different age groups and genders in the charts to explore the relationships between age, gender, region, and ethnicity group.

Select **Human Resource Sample** from the top navbar to return to the dashboard.

![Return to dashboard](media/sample-human-resources/power-bi-breadcrumbs.png)

## Compare currently active and former employees
Let’s explore data for currently active employees and employees who no longer work for the company.

On the dashboard, select the **Active Employee Count by Age Group** tile.  
![Active Employee Count by Age Group tile](media/sample-human-resources/pbi_hr_sample_activepie.png)

The Human Resources Sample report opens to the **Active Employees vs. Separations** page.  
![Active Employees vs. Separations page](media/sample-human-resources/hr5.png)

Items of interest:

* The two combo charts on the left show the year-over-year change for active employees and employee separations. We have more active employees this year due to rapid hiring, but also more separations than last year.
* In August, we had more separations compared to other months. Select the different age groups, genders, or regions to see if you can find any outliers.
* Looking at the pie charts, we notice we have an even split in our active employees by gender and age groups. Select different age groups to see how the gender split differs by age. Do we have an even split by gender in every age group?

## Reasons for separation
Let’s look at the report in Editing View. Select **Edit report** in the upper-left corner.

Change the pie charts to show employee separations data instead of active employees.

1. Select the **Active Employee Count by Age Group** pie chart.
2. In **Fields**, select **Employees** to expand the **Employees** table. Clear **Active Employee Count** to remove that field.
3. Select **Separation Count** in the **Employees** table to add it to the **Values** box in the **Fields** area.
4. On the report canvas, select the **Voluntary** bar in the **Separation Count by Separation Reason** bar chart. This bar highlights those employees who left voluntarily in the other visuals in the report.
5. Select the 50+ slice of the **Separation Count by Age Group** pie chart.

   Look at the line chart in the lower-right corner. This chart is filtered to show voluntary separations.  

   ![Employee separations over 50](media/sample-human-resources/pbi_hr_sample_sepsover50.png)

   Notice the trend in the 50+ age group. During the latter part of the year, more employees over age 50 left voluntarily. This trend is an area to investigate further with more data.

6. You can also follow the same steps for the **Active Employee Count by Gender** pie chart, changing it to separations instead of active employees. Look at the voluntary separation data by gender to see if you find any other insights.
7. Select **Human Resource Sample** from the top navbar to return to the dashboard. You can choose to save the changes you’ve made to the report.

## Bad hires
The last area to explore is bad hires. Bad hires are defined as employees who didn’t last for more than 60 days. We’re hiring rapidly, but are we hiring good candidates?

1. Select the **Bad Hires as % of Actives by Age Group** dashboard tile. The report opens to tab three, **Bad Hires**.

   ![Bad Hires as % of Actives by Age Group tile](media/sample-human-resources/hr7.png)  
2. Select **Northwest** in the **Region** box on the left and select **Male** in the **Bad Hire Count by Gender** donut chart. Look at the other charts on the **Bad Hires** page: notice there are more male bad hires than females and many Group A bad hires.
   ![Northwest bad hires](media/sample-human-resources/pbi_hr_sample_badhirespage.png)  
2. If you look at the **Bad Hire Count by Gender** donut chart and select different regions in the **Region** box, you'll notice that the East region is the only region with more female than male bad hires.  
3. Select the name of the dashboard from the top navbar to return to the dashboard.

## Ask a question in the Q&A box
In the [Q&A question box](power-bi-tutorial-q-and-a.md), you can ask a question about your data by using natural language. Q&A recognizes the words you type and figures out where in your dataset to find the answer.

1. Select the Q&A question box. Notice that even before you start typing, Q&A displays suggestions to help you form your question.

   ![Q&A box suggestions](media/sample-human-resources/pbi_hr_sample_qabox.png)

2. Enter the following text: *show age group, gender, and bad hires SPLY where region is east*.  

   ![Q&A box answers](media/sample-human-resources/pbi_hr_sample_qa_answer.png)

   Notice most of the female bad hires are under 30.

This environment is a safe one to play in. You can always choose not to save your changes. But if you do save them, you can select **Get Data** for a new copy of this sample.

## Next steps: Connect to your data
We hope this tour has shown how Power BI dashboards, Q&A, and reports can provide insights into human resources data. Now it's your turn; connect to your own data. With Power BI, you can connect to a wide variety of data sources. To learn more, see [Get started with the Power BI service](service-get-started.md).
