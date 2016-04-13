<properties
   pageTitle="Human Resources sample: Take a tour"
   description="Human Resources sample for Power BI: Take a tour"
   services="powerbi"
   documentationCenter=""
   authors="maggies"
   manager="mblythe"
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
   ms.date="02/22/2016"
   ms.author="amac"/>

# Human Resources sample for Power BI: Take a tour  

The HR department has the same reporting model across different companies, even when they differ by industry or size. This sample looks at new hires, active employees, and employees who left and tries to uncover any trends in the hiring strategy. Our main objectives are to understand:

- Who we hire.
- Biases in our hiring strategy.
- Trends in voluntary separations.

This sample is part of a series that illustrates how you can use Power BI with business-oriented data, reports, and dashboards. This is real data from obviEnce ([www.obvience.com)](http://www.obvience.com/) that has been anonymized.

![](media/powerbi-sample-human-resources-take-a-tour/pbi_hr_sample_dash.png)

Want to follow along? In the [Power BI service](https://powerbi.com), go to **Get Data > Samples > Human Resources Sample > Connect** to get your own copy of the sample.

You can also [download just the dataset (Excel workbook)](http://go.microsoft.com/fwlink/?LinkId=528592) for this sample.

## New hires  
Let’s explore new hires first.

1.  In the left navigation pane, select the Human Resources dashboard.
2.  Select the **New Hire Count, New Hires Same Period Last Year, Actives YoY % Change** **By Month** tile.  
    ![](media/powerbi-sample-human-resources-take-a-tour/hr2.png)  

    The Human Resources Sample report opens to the **New Hires** page.  

    ![](media/powerbi-sample-human-resources-take-a-tour/hr3.png)

Notice the following:

- The **New Hire Count, New Hires SPLY and Actives YoY % Change by Month** combo chart shows we hired more people every month this year compared to last year &#151; significantly more people in some months.

- In the combo chart **New Hire Count and Active Employee Count by Region and Ethnicity**, notice we’re hiring fewer people in the **East** region.

- The **New Hires YoY Var by Age Group** waterfall chart shows we’re hiring mainly younger people. This may be due to the mainly part-time nature of the jobs.

- The **New Hire Count by Gender** pie chart shows a pretty even split.

Can you find more insights &#151; for example, a region where the gender split is not even? Select different age groups and genders in the charts to explore the relationships between age, gender, region, and ethnicity group.

Select **Power BI** in the top navigation bar to return to the dashboard.

## Compare current active and former employees  
Let’s explore data for current active employees and employees who no longer work for the company.

On the dashboard, select the **Active Employee Count by Age Group** tile.  
![](media/powerbi-sample-human-resources-take-a-tour/pbi_hr_sample_activepie.png)

The Human Resources Sample report opens to the **Active Employees vs. Separations** page.  
![](media/powerbi-sample-human-resources-take-a-tour/hr5.png)

Items of interest:

- Combo charts on the left show year-over-year change for active employees and separates. We have more actives this year due to rapid hiring, but also more separates than last year.

- In August we had more separates compared to other months. Select the different age groups, genders, or regions to see if you can find any outliers.

- Looking at the pie charts, we notice we have a pretty even split in our active employees by gender and age groups. Select different age groups to see the gender split differs by age. Do we have an even split by gender in every age group? 

## Reasons for separation  
Let’s look at the report in Editing View. Select **Edit report** in the upper-left corner. 

Change the pie charts to show Separates data instead of Actives.

1.  Select the **Active Employee Count by Age Group** pie chart.

2.  In **Fields**, select the arrow next to **Employees** ﻿to expand the Employees table. Clear the check box next to **Active Employee Count**﻿ to remove that field.

3.  Select the check box next to **Separation Count** in the Employees table to add it to the **Values** box in the field well.

4.  Select the **Voluntary** bar in the **Separation Count by Separation Reason** bar chart. This highlights those who left voluntarily in the other visuals in the report.

5.  Click the 50+ slice of the Separation Count by Age Group pie chart.

    Look at the Separations by Reason line chart in the lower-right corner. This chart is filtered to show voluntary separations.  
    ![](media/powerbi-sample-human-resources-take-a-tour/pbi_hr_sample_sepsover50.png)

    Notice the trend in the 50+ age group? During the latter part of the year more employees over age 50 are leaving voluntarily. This would be an area to investigate further with more data.

6.  You can follow the same steps for the **Active Employee Count by Gender** pie chart too, changing it to separations instead of active employees. Look at the voluntary separation data by gender to see if you find any other insights.

7.  Click **Power BI** in the top navigation bar to return to the dashboard. You can save the changes you’ve made to the report or not.

## Bad hires  
The last area to explore is bad hires. Bad hires are defined as employees who didn’t last for more than 60 days. We’re hiring rapidly. Are we hiring good candidates?

1.  Select the **Bad Hires as % of Actives by Age Group** dashboard tile. This opens the report to page 3, “Bad Hires”.

    ![](media/powerbi-sample-human-resources-take-a-tour/hr7.png)  

2.  Select the **Northwest**﻿ check box in the Region slicer on the left and the **Male** slice in the Bad Hire Count by Gender donut chart.  Look at other charts on the “Bad Hires” page. More male bad hires than females and lot of Group A bad hires.
    ![](media/powerbi-sample-human-resources-take-a-tour/pbi_hr_sample_badhirespage.png)  

3.  Looking at the **Bad Hires by Gender** donut chart and clicking through the **Region** slicer we notice that East is the only region with more female than male bad hires.  

4.  Click **Power BI** in the top navigation bar to return to the dashboard.

## Asking a question in the Q&A box
The [Q&A question box](powerbi-service-how-to-use-q-and-a.md) is where you type a question using natural language. Q&A recognizes the words you type and figures out where in your dataset to find the answer.

1.  Click in the Q&A question box. Notice before you even start typing, the Q&A box contains suggestions:

    ![](media/powerbi-sample-human-resources-take-a-tour/pbi_hr_sample_qabox.png)

2.   You can pick one of those suggestions, or type:

    **show age group, gender and bad hires where region is east**.  

    ![](media/powerbi-sample-human-resources-take-a-tour/pbi_hr_sample_qa_answer.png)

    Notice most of the female bad hires are under 30.
2.  Click the back arrow ![](media/powerbi-sample-human-resources-take-a-tour/backarrow.png) to go back to the dashboard.

This is a safe environment to play in. You can always choose not to save your changes. If you do save them, you can always go to **Get Data** for a new copy of this sample.

## Next steps: Connect to your data  
We hope this tour has shown how Power BI dashboards, Q&A, and reports can provide insights into human resources data. Now it is your turn — connect to your own data. With Power BI you can connect to a wide variety of data sources. Learn more about [getting started with Power BI](powerbi-service-get-started.md).  
