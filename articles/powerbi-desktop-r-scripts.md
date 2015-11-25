<properties
   pageTitle="Running R Scripts in Power BI Desktop (Beta)"
   description="Running R Scripts in Power BI Desktop (Beta)"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   editor=""
   tags=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="11/16/2015"
   ms.author="davidi"/>

# Running R Scripts in Power BI Desktop (Beta)  

You can run R scripts directly in Power BI Desktop, and import the resulting datasets into a Power BI Desktop data model.

### Installing R

To run R scripts in Power BI Desktop, you need to install **R** on your local machine. You can download and install **R** for free from many locations, including the [Revolution Open download page](https://mran.revolutionanalytics.com/download/), and the [CRAN Repository](https://cran.r-project.org/bin/windows/base/).

### Running R Scripts
With just a few steps in Power BI Desktop you can run R scripts and create a data model, from which you can create reports, and share them on the Power BI service.

#### Prepare an R Script
To run an R script in Power BI Desktop, create the script in your local R development environment, and make sure it runs successfully.

To run the script in Power BI Desktop, make sure the script runs successfully in a new and unmodified workspace. This means that all packages and dependencies must be explicitly loaded and run. You can use *source()* to run dependent scripts.

When preparing and running an R script in Power BI Desktop, there are a few limitations:
-   Only data frames are imported, so make sure the data you want to import to Power BI is represented in a data frame
-   Columns that are typed as Complex and Vector are not imported, and are replaced with error values in the created table.
-   Values that are N/A are translated to NULL values in Power BI Desktop
-   Any R script that runs longer than 30 minutes times out
-   Interactive calls in the R script, such as waiting for user input, halts the script’s execution
-   When you set your working directory in your R script, you *must* define a full path to the working directory, rather than a relative path. 

#### Run your R Script and Import Data

1.   In Power BI Desktop, the R Script data connector is found in **Get Data**. To run your R Script, select **Get Data &gt; More...**, then select **Other &gt; R Script (Beta)** as shown in the following image.

    ![](media/powerbi-desktop-r-scripts/r-scripts-1.png)

2.   If R is installed on your local machine, the latest installed version is selected as your R engine. Simply copy your script into the script window and select **OK**.

    ![](media/powerbi-desktop-r-scripts/r-scripts-2.png)

3.   If R is not installed, is not identified, or if there are multiple installations on your local machine, expand **R Installation Settings** to display installation options, or to select which installation you want to run the R script.

    ![](media/powerbi-desktop-r-scripts/r-scripts-3.png)

    If R is installed is not identified, you can explicitly provide its location in the text box provided when you expand **R Installation Settings**. In the above image, the path *C:\Program Files\R\R-3.2.0* is explicitly provided in the text box.

4.   Select **OK** to run the R Script. When the script runs successfully, you can then choose the resulting data frames to add to the Power BI model.

#### Refresh
You can refresh an R script in Power BI Desktop. When you refresh an R script, Power BI Desktop runs the R script again in the Power BI Desktop environment.

You can also enable refresh, and scheduled refresh, for R script reports published to the Power BI service. To enable refresh for data published to the Power BI service, confirm you have the latest version of the [personal gateway](powerbi-personal-gateway.md) installed and properly configured on the computer running the R script, and ensure the personal gateway is configured with the account that has access to the data being refreshed.
