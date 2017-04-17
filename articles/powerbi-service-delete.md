﻿<properties
   pageTitle="Delete a dashboard, report, workbook, dataset, or workspace from Power BI"
   description="Learn how to delete almost anything from Power BI"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
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
   ms.date="04/16/2017"
   ms.author="mihart"/>

#  Delete almost anything in Power BI service
This article teaches you how to delete a dashboard, report, workbook, dataset, app, and workspace in Power BI service.

## Delete a dashboard

Dashboards can be removed. Removing the dashboard does not delete the underlying dataset or any reports associated with that dashboard.

-   If you are the owner of the dashboard, you can remove it. If you've shared the dashboard with colleagues, removing the dashboard from your Power BI workspace will remove the dashboard from their Power BI workspace.

-   If a dashboard is shared with you and you no longer want to see it, you can remove it.  Removing a dashboard does not remove it from anyone else's Power BI workspace.

-   If a dashboard is part of an [organizational content pack](powerbi-service-organizational-content-pack-delete.md), the only way to remove it is to remove the associated dataset.

### To delete a dashboard  
1.  In your workspace, select the **Dashboards** tab.

2. Locate the dashboard to delete and select the Delete icon ![](media/powerbi-service-delete/power-bi-delete-icon.png). 

    ![](media/powerbi-service-delete/power-bi-delete-dash.gif)


## Delete a report  

Don't worry, deleting a report does not delete the dataset that the report is based on.  And any visualizations that you pinned from the report are also safe -- they remain on the dashboard until you delete them individually.

### To delete a report  
1.  In your workspace, select the **Reports** tab.

2. Locate the report to delete and select the Delete icon   ![](media/powerbi-service-delete/power-bi-delete-icon.png).   

    ![](media/powerbi-service-delete/power-bi-delete-reportnew.png)

3.  Confirm the deletion.

    ![](media/powerbi-service-delete/power-bi-delete-report.png)

> [AZURE.NOTE] If the report is part of a [content pack](powerbi-service-organizational-content-packs-introduction.md), you will not be able to delete it using this method.  See [Deleting an organizational content pack](powerbi-service-organizational-content-pack-delete.md).

## Delete a workbook  

Workooks can be removed. However, removing a workbook also removes all reports and dashboard tiles that contain data from this workbook.

If the workbook is stored on OneDrive for Business, deleting it from Power BI does not delete it from OneDrive.

### To delete a workbook  
1.  In your workspace, select the **Workbooks** tab.

2. Locate the workbook to delete and select the Delete ![](media/powerbi-service-delete/power-bi-delete-report2.png) icon.

    ![](media/powerbi-service-delete/power-bi-delete-workbooknew.png)

3.  Confirm the deletion.

    ![](media/powerbi-service-delete/power-bi-delete-confirm.png)



## Delete a dataset  

Datasets can be deleted. However, deleting a dataset also deletes all reports and dashboard tiles that contain data from this dataset.

If a dataset is part of one or more [organizational content packs](powerbi-service-organizational-content-pack-delete.md), the only way to delete it is to remove it from the content packs where it's being used, wait for it to be processed, and then try deleting it again.

### To delete a dataset  
1.  In your workspace, select the **Datasets** tab.

2. Locate the dataset to delete and select the ellipses (...).  

    ![](media/powerbi-service-delete/power-bi-delete-datasetnew.png)

2.  From the dropdown, select **Delete**.

    ![](media/powerbi-service-delete/power-bi-delete-datasetnew2.png)

3.  Confirm the deletion.

    ![](media/powerbi-service-delete/power-bi-delete-dataset-confirm.png)


##  Delete or remove an App workspace
App workspaces can be removed from your Power BI by leaving the group. Leaving a group does not delete the group for other members. If you own the group, you can delete it. Deleting the group does delete it from all members workspaces as well.

###    To delete or remove an App workspace

1.  Start in the app workspace you'd like to remove.

2. In the top-right corner, select the ellipses (...) and:

    -    To delete the app workspace, choose **Edit group** and at the bottom of the **Edit group** window, select **Delete group**.

      ![](media/powerbi-service-delete/power-bi-edit-group.png)

    -    To remove the app workspace, choose **Leave group** and then select **Leave**.

      ![](media/powerbi-service-delete/power-bi-leave-group.png)

##  Delete or remove an App
Apps can be removed from your Power BI Apps canvas. If you remove an app accidentally, you have several options for getting it back.  You can ask the App creator to re-send it, you can find the original email with the link to the app, and you can check your Notifications center to see if the notification for that app is still listed.

###    To delete or remove an app

1.  In your left navpane, select **Apps** to open the Apps canvas. 

2.    Hover over the app to delete, and select the Delete ![](media/powerbi-service-delete/power-bi-delete-report2.png)  icon.

      ![](media/powerbi-service-delete/power-bi-app-menu.png)


## Considerations and troubleshooting
This article covered how to delete the major building blocks of Power BI service. But there are more things that you can delete in Power BI.  

-    [Remove your Featured dashboard](powerbi-service-featured-dashboards#change-the-featured-dashboard.md)

-    [Remove (unfavorite) a dashboard](powerbi-service-favorite-dashboards#unfavorite-a-dashboard.md)

-    [Delete a report page](powerbi-service-delete-a-page-from-a-report.md)

-    [Delete a dashboard tile](powerbi-service-edit-a-tile-in-a-dashboard.md)

-    [Delete a report visualization](powerbi-service-delete-a-visualization.md)

More questions? [Try the Power BI Community](http://community.powerbi.com/) 
