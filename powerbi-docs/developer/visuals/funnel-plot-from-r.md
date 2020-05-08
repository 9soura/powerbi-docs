---
title: Build a funnel plot from R script to R visual
description: This article describes how to build a funnel plot from R script to R Power BI visual.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 04/02/2020
---

# Tutorial: Build a funnel plot from R script to R visual
This article describes how to build a funnel plot using R script in R visual step by step.

In this article, you learn how to create:

> [!div class="checklist"]
>
> * an R-script for RStudio
> * an R-visual in Power BI
> * a *PNG-based* R-powered Visual in Power BI
> * a *HTML-based* R-powered Visual in Power BI

The funnel plot provides an easy way to consume, interpret, and show the amount of expected variation. The **funnel** is formed using confidence limits and outliers are shown as dots outside the funnel.

![funnel plot image](./media/funnel-plot/fp.jpg)

This example is based on the [inspiring story](https://www.theguardian.com/commentisfree/2011/oct/28/bad-science-diy-data-analysis) about how using the wrong visualization tools can lead to the wrong conclusion. The hero of this story is the funnel plot, which is used to compare and analyze institutional performance and medical data.  

For more information, see [this blog ](https://onlinejournalismblog.com/2011/10/31/power-tools-for-aspiring-data-journalists-funnel-plots-in-r/) to further demonstrate implementations of a funnel plot in R.

## Build an R script with dataset

1. Download a [minimal R script](./samples/funnel-plot/chapter1_R/script_R_v1_00.r) and its accompanying data table, [dataset.csv](./samples/funnel-plot/chapter1_R/dataset.csv).

1. Next, edit the script to mirror [this script](./samples/funnel-plot/chapter1_R/script_R_v1_01.r). This adds input error handling and user parameters to control the plot's appearance.

## Build a report

Next, edit the script to mirror [this script](./samples/funnel-plot/chapter2_R/script_R_v2_00.r). This loads *dataset.csv* instead of *read.csv* into the Power BI desktop workspace and creates a **Cancer Mortality** table. See the results in the following [PBIX file](./samples/funnel-plot/chapter2_R/funnelPlot_Rvisual.pbix).

> [!NOTE]
> The `dataset` is a hard-coded name for the input `data.frame` of any R-visual. 

## Create an R-powered visual and package in R code

1. Before you begin, be sure to [install PBIVIZ tools](./custom-visual-develop-tutorial.md#installing-packages).

1. Run the following command to create a new R-powered visual:

   ```bash
   pbiviz new funnelRvisual -t rvisual
   cd funnelRvisual
   npm install 
   pbiviz package
   ```

   This command creates the folder *funnelRvisual* with initial template visual (`-t` for **template**). The PBIVIZ can be found in the *dist* folder, the R-code inside *script.r* file. Try to import it into Power BI and see what happens.

1. Edit *script.r* file and replace the contents with your previous script.

1. Edit *capabilities.json* and replace the string `Values` with `dataset`. This replaces the name of "Role" in the template to be like in R-code.

   ![before vs. after](./samples/funnel-plot/chapter3_R/funnelRvisual_v01/capabilities_changes.PNG)

1. *(optional)* Edit *dependencies.json* and add a section for each R package required by the R script. This tells Power BI to automatically import these packages when the visual is loaded for the first time.

   ![before vs. after](./samples/funnel-plot/chapter3_R/funnelRvisual_v01/dependencies_changes.PNG)

1. Re-package the visual using the `pbiviz package` command and try to import it into Power BI.

download [PBIX](./samples/funnel-plot/chapter3_R/funnelPlot_RCustomVisual.pbix) and [source code](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v01/).

## Make R-based visual improvements

The visual is not yet user-friendly because the user has to know the order of columns in the input table.

1. Divide the input field `dataset` into 3 fields (roles): `Population`, `Number` and `Tooltips`

   ![CV01to02](./media/funnel-plot/Capture01TO02.PNG)

1. Edit *capabilities.json* and replace the `dataset` role with the three new roles. You'll need to update sections: `dataRoles` and `dataViewMappings`, which define names, types, tooltips, and maximum columns for each input field.

   ![](./samples/funnel-plot/chapter3_R/funnelRvisual_v02/capabilities_before_vs_after.png)
   
   download [capabilities.json](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v02/capabilities.json), see [capabilities](./capabilities.md) for more information

1. Edit *script.r* to support `Population`, `Number` and `Tooltips` as input dataframes instead of `dataset`.

   ![](./samples/funnel-plot/chapter3_R/funnelRvisual_v02/script_r_before_vs_after.png)

   download [script.r](./samples/funnel-plot/chapter3_R/funnelRvisual_v02/script.r)

   > [!NOTE]
   > To follow the changes in R-script, search for comment blocks: 
   > 
   > ```r
   > #RVIZ_IN_PBI_GUIDE:BEGIN: Added to enable visual fields
   > ...
   > #RVIZ_IN_PBI_GUIDE:END: Added to enable visual fields
   > 
   > #RVIZ_IN_PBI_GUIDE:BEGIN: Removed to enable visual fields 
   > ...
   > #RVIZ_IN_PBI_GUIDE:BEGIN: Removed to enable visual fields
   > ```

1. Re-package the visual using the `pbiviz package` command and try to import it into Power BI.

download [PBIX](./samples/funnel-plot/chapter3_R/funnelPlot_RCustomVisual.pbix) and [source code](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v02)

## Add user parameters

1. Add capabilities for the user to control colors and sizes of visual elements including internal parameters from the UI.

   ![CV02to03](./media/funnel-plot/Capture02TO03.PNG)

1. Edit *capabilities.json* and update the `objects` section. Here we define names, tooltips and types of each parameter, and also decide on the partition of parameters into groups (three groups in this case).

   download [capabilities.json](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/capabilities.json), see [object properties](./objects-properties.md) for more information

   ![](./samples/funnel-plot/chapter3_R/funnelRvisual_v03/capabilities_before_after.PNG)

1. Edit *src/settings.ts* to mirror [this settings.ts](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/src/settings.ts). This file is written in TypeScript.  

   Here you will find two blocks of the code added to:
   - Declare new interface to hold the property value
   - Define a member property and default values

   ![](./samples/funnel-plot/chapter3_R/funnelRvisual_v03/settings_ts_before_after.PNG)

1. Edit *script.r* to mirror [this script.r](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/script.r). This adds support for the parameters in the UI by adding `if.exists` calls per user-parameter.

   > [!NOTE]
   > To follow the changes in R-script, search for comments:
   >
   > ```r
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Added to enable user parameters
   >  ...
   > #RVIZ_IN_PBI_GUIDE:END:Added to enable user parameters
   >
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Removed to enable user parameters 
   >  ...
   > #RVIZ_IN_PBI_GUIDE:END:Removed to enable user parameters
   > ```

   ![](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/script_r_before_after_1.png)

   You can decide not to expose the parameters to the UI, like we did.  

1. Re-package the visual using the `pbiviz package` command and try to import it into Power BI.

download [PBIX](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelPlot_RCustomVisual.pbix) and [source code](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/)

> [!NOTE]
> Here we added parameters of several types (boolean, numeric, string, and color) all at once. For a simple case, please see [this example](https://github.com/Microsoft/PowerBI-visuals/blob/master/RVisualTutorial/PropertiesPane.md) on how to add a single parameter. 

## Convert visual to RHTML-based visual

Since the resulting visual is PNG-based, it isn't responsive to mouse hover, can't be zoomed in on, etc., so we need to convert it to an HTML-based visual. We'll create an empty R-powered HTML-based Visual template, then copy some scripts from the PNG-based project.

1. Run the command:

   ```bash
   pbiviz new funnelRHTMLvisual -t rhtml
   cd funnelRHTMLvisual
   npm install 
   pbiviz package
   ```

1. Open *capabilities.json* and note the `"scriptOutputType":"html"` line.

1. Open *dependencies.json* and note the names of the listed R-packages.

1. Open *script.r* and note the structure. You can open and run it in RStudio since it does not use external input. 

   Note that it creates and saves *out.html*. This file is self-contained (with no external dependencies) and defines the graphics inside the HTML widget. 

   > [!NOTE]
   > For `htmlWidgets` users, R-utilities are provided in the [r_files folder](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/r_files) to help convert `plotly` or `widget` objects into self-content HTML. 
   > 
   > This version of R-powered visual also supports the `source` command (unlike previous types of visuals), to make your code more readable.   
 
1. Replace *capabilities.json* with the *capabilities.json* from the previous step, but be sure to keep:

   `"scriptOutputType": "html"`  

   download [capabilities.json](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/capabilities.json).

1. Merge the latest version of *script.r* with the *script.r* from the template.

   The new script uses the `plotly` package to convert the **ggplot** object into a **plotly** object, then the `htmlWidgets` package to save it to an HTML file. 

   Most of the utility functions are moved to [_r_files/utils.r_](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/r_files/utils.r) and the `generateNiceTooltips` function is added for the appearance of the **plotly** object.

   download [script.r](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/script.r)

   ![1](./samples/funnel-plot/chapter4_R/RHTML_v01/script_befor_after_1.PNG)
   
   ![2](./samples/funnel-plot/chapter4_R/RHTML_v01/script_befor_after_2.PNG)

   > [!NOTE]
   > To follow the changes in R-script, search for comments:
   > 
   > ```r
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Added to create HTML-based 
   >  ...
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Added to create HTML-based
   >
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Removed to create HTML-based  
   > ...
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Removed to create HTML-based
   > ```

1. Merge the latest version of *dependencies.json* with the *dependencies.json* from the template, to include new R-package dependencies.

   download [dependencies.json](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/dependencies.json)

1. Edit *src/settings.ts* the same way from previous steps.

1. Re-package the visual using the `pbiviz package` command and try to import it into Power BI.

download [PBIX and source code](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01)

## Build additional examples

1. Run the following command to create an empty project: 

   ```bash
   pbiviz new smallRHTML -t rhtml
   cd smallRHTML
   npm install 
   pbiviz package
   ```

1. Take code from this [showcase](http://www.htmlwidgets.org/showcase_networkD3.html) and make the highlighted changes:

   ![Highlighted changes](./media/funnel-plot/CaptureNetworkD3.PNG)

1. Replace your template's *script.r* and run `pbiviz package` again. Now the visual is included in your Power BI report!

## Tips and tricks

* We recommend that developers edit *pbiviz.json* to store correct metadata, such as **version**, **email**, **name**, **license type**, etc.

   > [!IMPORTANT]
   > The **guid** field is the unique identifier for a visual. If you create a new project for each visual, the GUID will be also be different. It's only the same when using an old project copied to a new visual, which you shouldn't do.

* Edit [*assets/icon.png*](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/assets/icon.png) to create unique icons for your visual. 

* To debug R-code in RStudio using the same data as in your Power BI report, add the following to the beginning of the R-script (edit the `fileRda` variable):

   ```r
   #DEBUG in RStudio
   fileRda = "C:/Users/yourUserName/Temp/tempData.Rda"
   if(file.exists(dirname(fileRda)))
   {
     if(Sys.getenv("RSTUDIO")!="")
       load(file= fileRda)
     else
       save(list = ls(all.names = TRUE), file=fileRda)
   }
   ```

   This saves the environment from a Power BI report and loads it into RStudio. 

* You don't need to develop R-powered Visuals from scratch with code available on [Github](https://github.com/Microsoft?utf8=%E2%9C%93&q=PowerBI&type=&language=R). Simply select the visual to use as a template and copy the code into a new project.

   For example, try using the [spline custom visual](https://github.com/Microsoft/PowerBI-visuals-spline).

* Each R Visual applies the `unique` operator to its input table. To avoid identical rows being removed, consider adding an extra input field with a unique ID and ignore it in the R code.   

* If you have a Power BI account, use the Power BI service to develop a visual [on-the-fly](/PowerBI-visuals/docs/step-by-step-lab/creating-a-custom-visual/#testing-the-custom-visual) instead of re-packaging them with the `pbiviz package` command.

### HTML widgets gallery
Explore visuals in the [HTML widgets gallery](http://gallery.htmlwidgets.org/) for use in your next visual. To make things easy, we've created a [visuals project repo](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/multipleRHTML) with over 20 interactive HTML visuals to choose from!

> [!NOTE]
> To switch between html widgets use **Format** > **Settings** > **Type**.  Try it out with [this PBIX file](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/multipleRHTML/assets/sample.pbix). 

#### To use a sample for your visual

1. Download the entire folder.
1. Edit *script.r* and *dependencies.json* to keep only one widget.
1. Edit *capabilities.json* and *settings.ts* to remove the `Type` selector.
1. Change `const updateHTMLHead: boolean = true;` to `false` in *visual.ts*. *(for better performance)*
1. Change metadata in *pbiviz.json*, most importantly the `guid` field.
1. Re-package and continue to customize the visual as desired. 

![CV02to03](./media/funnel-plot/CaptureSample.PNG)

![CV02to03](./media/funnel-plot/CaptureSampleService.PNG)

> [!NOTE]
> Not all widgets in this project are supported by the service.

## Next steps

To learn more, see additional tutorials on [PowerBI visuals](./custom-visual-develop-tutorial.md) and [R visuals](/power-bi/visuals/service-r-visuals).

Learn how to [develop and submit visuals](https://powerbi.microsoft.com/en-us/documentation/powerbi-developer-office-store/) to the [Office Store (gallery)](https://store.office.com/en-us/appshome.aspx?ui=en-US&rs=en-US&ad=US&clickedfilter=OfficeProductFilter%3aPowerBI&productgroup=PowerBI), or for further examples, see the [R-script showcase](https://community.powerbi.com/t5/R-Script-Showcase/bd-p/RVisuals)
