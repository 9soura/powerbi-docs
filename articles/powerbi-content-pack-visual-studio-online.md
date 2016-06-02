﻿<properties 
   pageTitle="Visual Studio Online content pack"
   description="Visual Studio Online content pack for Power BI"
   services="powerbi" 
   documentationCenter="" 
   authors="theresapalmer" 
   manager="mblythe" 
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
   ms.date="05/17/2016"
   ms.author="tpalmer"/>
# Visual Studio Online content pack for Power&nbsp;BI

Use the Visual Studio Online content pack for Power BI to gain insights into your git and TFVC team projects. After you make a connection, your data comes to you automatically on a dashboard and in reports. 

Connect to the [Visual Studio Online content pack](https://app.powerbi.com/getdata/services/visual-studio-online) or read more about the [Visual Studio Online integration](https://powerbi.microsoft.com/integrations/visual_studio_online) with Power BI.

Note: This content pack requires access to the VSO account which has OAuth enabled. More details on requirements below.

## How to connect

1.  Select **Get Data** at the bottom of the left navigation pane.  
    ![](media/powerbi-content-pack-visual-studio-online/PBI_GetData.png) 

2.  In the **Services** box, select **Get**.  
    ![](media/powerbi-content-pack-visual-studio-online/PBI_GetServices.png) 

3.  Select the **Visual Studio Online** content pack and click **Get**.     
    ![](media/powerbi-content-pack-visual-studio-online/vsts.png)

4.  Enter information about your Visual Studio Online account. See details on [finding these parameters](#FindingParams) below.

    ![](media/powerbi-content-pack-visual-studio-online/PBI_VSOSignIn.png)

    Your account name is the front of your URL to visualstudio.com:    
    ![](media/powerbi-content-pack-visual-studio-online/URLimage.png)

    Your Project name is the name you see at the top of every page in VSO:  
	![](media/powerbi-content-pack-visual-studio-online/Projectimage.png)

5.  Authenticate with Visual Studio Online using oAuth2. You may see a VSO sign-in dialog box as a result.  

	>**Important:** Some Visual Studio Online deployments don't support oAuth2.  Follow the guidance in the Troubleshooting section if sign-in fails.

    ![](media/powerbi-content-pack-visual-studio-online/PBI_VSOSignIn2.png)

6.  Follow the Visual Studio Online authentication screens to grant the Visual Studio content pack for Power BI permission to your team project data.   
    ![](media/powerbi-content-pack-visual-studio-online/VSOAuthorizeApp450.png)

7.  After you connect to your Visual Studio Online project, you see a new dashboard, report, and dataset in the left navigation pane. New items are marked with a yellow asterisk \*.  
    ![](media/powerbi-content-pack-visual-studio-online/VisualStudioOnline800px.png) 


**What Now?**

- Try [asking a question in the Q&A box](powerbi-service-q-and-a.md) at the top of the dashboard

- [Change the tiles](powerbi-service-edit-a-tile-in-a-dashboard.md) in the dashboard.

- [Select a tile](powerbi-service-dashboard-tiles.md) to open the underlying report.

- While your dataset will be schedule to refreshed daily, you can change the refresh schedule or try refreshing it on demand using **Refresh Now**


## What's included

Visual Studio Online in Power BI provides a variety of tables and fields for your reporting. The full list of what is included in the content pack can be found here:  <https://www.visualstudio.com/get-started/report/vso-pbi-whats-available-vs>

## System requirements

-   Access to the Visual Studio Online account with permission to collect the data using the REST API.  
-   Permission granted to the “Power BI for VSO” application during initial connection. To disconnect Power BI and remove its authorization to access your Visual Studio Online account, you can Revoke access in Visual Studio Online. See <https://www.visualstudio.com/get-started/setup/change-application-access-policies-vs>.  

More details can be found at <https://www.visualstudio.com/en-us/get-started/report/connect-vso-pbi-vs>.

<a name="FindingParams"></a>
## Finding parameters 

Your account name is the front of your URL to visualstudio.com:    
    ![](media/powerbi-content-pack-visual-studio-online/URLimage.png)

Your Project name is the name you see at the top of every page in VSO:  
	![](media/powerbi-content-pack-visual-studio-online/Projectimage.png)

You can also use wildcards to select multiple projects. For example, you can select all projects by entering just “\*”, or all projects that start with “Azure” by entering “Azure\*”.

## Troubleshooting
  
When you attempt to login to your Visual Studio Online, you may receive a Login failed message.  
![](media/powerbi-content-pack-visual-studio-online/loginerror.png)

There are two common reasons why you may not be able to authenticate successfully:

1) You are signed in with a personal account, rather than your work or school account  

2) Your Visual Studio Online deployment does not support oAuth 

**Signing in with your work or school account**  
If you see this issue, it may mean that you’re already authenticated with Visual Studio Online under a different account than the account you’re trying to load data from – for example, if you have connected to Visual Studio Online with a personal Microsoft account, and connected to PowerBI with a work or school account.

To resolve this:  
-   Cancel out of the configuration dialog  
-   Sign out of Visual Studio Online under your personal account  
-   Sign into Visual Studio Online using your work or school account  
-   Restart the “Get data” process above  

Connecting with your work or school account (Azure Active Directory / AAD):  
    ![](media/powerbi-content-pack-visual-studio-online/vsologinscreen.png)

If you see this dialog, and you want to connect with your work or school account (Azure Active Directory), make sure to click the link on the left to sign in with that account – do not provide your AAD credentials on the right hand side, as that is expecting a Microsoft account (your personal account).

**Visual Studio Online deployments that do not support oAuth2**  
Your VSO administrator may have disabled oAuth for your Visual Studio Online deployment.  When this happens you will not be able to use the Visual Studio content pack for Power BI at this time.  

![](media/powerbi-content-pack-visual-studio-online/oauth.png)

### See also
- [Get started with Power BI](powerbi-service-get-started.md)
- [Get data](powerbi-service-get-data.md)
