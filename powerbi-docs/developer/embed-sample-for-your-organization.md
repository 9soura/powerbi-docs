---
title: Embed Power BI content into an application for your organization
description: Learn how to integrate, or embed, a report, dashboard or tile into a web app using the Power BI APIs for your organization.
author: markingmyname
ms.author: maghan 
ms.date: 07/13/2018
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
#Customer intent: As a developer, I want to embed Power BI content into an application, so users of my organization can share data.
---
# Tutorial: Embed a Power BI report, dashboard or tile into an application for your organization
With **Power BI**, you can embed reports, dashboards, or tiles into an application using **user owns data**. **User owns data** is about having an application that allows you to extend the Power BI service. This requires that users of your application sign into Power BI when they want to view their content. Once someone in your organization signs in, they will only have access to content that they own or that have been shared with them in the Power BI service. This tutorial demonstrates how to integrate a report into an application using the **Power BI .NET SDK** along with the **Power BI JavaScript API** when embedding **Power BI** into an application for your organization using **user owns data**.

In this tutorial, you learn how to:
>[!div class="checklist"]
>* Register an application in Azure.
>* Embed a Power BI report into an application.

## Prerequisites
To get started, you need a **Power BI Pro** account and a **Microsoft Azure** subscription.

* If you're not signed up for **Power BI Pro**, [sign up for a free trial](https://powerbi.microsoft.com/en-us/pricing/) before you begin.
* If you don’t have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.
* You need to have your own [Azure Active Directory tenant ](create-an-azure-active-directory-tenant.md) setup.
* You need [Visual Studio](https://www.visualstudio.com/) installed (version 2013 or later).

## Setup your embedded analytics development environment

Before you start embedding reports, dashboard, or tiles into your application, you need to make sure your environment is set up to allow for embedding. As part of the setup, you need to do the following.

You can go through the [Onboarding experience tool](https://aka.ms/embedsetup/UserOwnsData) to quickly get started and download a sample application that helps you walk through creating an environment and embedding a report.

However, if you choose to set up the environment manually, you can continue below.
### Register an application in Azure Active Directory (Azure AD)

You register your application with Azure Active Directory to allow your application access to the Power BI REST APIs. This allows you to establish an identity for your application and specify permissions to Power BI REST resources.

1. Accept the [Microsoft Power BI API Terms](https://powerbi.microsoft.com/api-terms).

2. Sign into the [Azure portal](https://portal.azure.com).

    ![Azure Portal Main](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

3. In the left-hand navigation pane, choose **All Services**, select **App Registrations** and then select **New application registration**.

    ![App registration search](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)</br>
    ![New App registration](media/embed-sample-for-your-organization/embed-sample-for-your-organization-004.png)

4. Follow the prompts and create a new application. For **user owns data** you need to use **Web app/API** for the application type. You also need to provide a **Sign-on URL**, which **Azure AD** uses to return token responses. Enter a value specific to your application (for example: http://localhost:13526/).

    ![Create App](media/embed-sample-for-your-organization/embed-sample-for-your-organization-005.png)

### Apply permissions to your application within Azure Active Directory

You need to enable additional permissions for your application in addition to what was provided on the app registration page. You need to be logged in with the *master* account, used for embedding, which needs to be a global admin account.

### Use the Azure Active Directory portal

1. Browse to [App registrations](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) within the Azure portal and select the app that you are using for embedding.

    ![Choosing App](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

2. Select **Settings**, then under **API Access** select **Required permissions**.

    ![Required Permissions](media/embed-sample-for-your-organization/embed-sample-for-your-organization-008.png)

3. Select **Windows Azure Active Directory** and then make sure **Access the directory as the signed-in user** is selected. Select **Save**.

    ![Windows Azure AD Permissions](media/embed-sample-for-your-organization/embed-sample-for-your-organization-011.png)

4. Select **Add**.

    ![Add Permissions](media/embed-sample-for-your-organization/embed-sample-for-your-organization-012.png)

5. Select **Select an API**.

    ![Add API Access](media/embed-sample-for-your-organization/embed-sample-for-your-organization-013.png)

6. Select **Power BI Service**, then select **Select**.

    ![Select PBI Services](media/embed-sample-for-your-organization/embed-sample-for-your-organization-014.png)

7. Select all permissions under **Delegated Permissions**. You need to select them one by one to save the selections. Select **Save** when done.

    ![Select delegated permissions](media/embed-sample-for-your-organization/embed-sample-for-your-organization-015.png)

## Setup your Power BI environment

### Create an app workspace

If you are embedding reports, dashboards, or tiles for your customers, then you have to place your content within an app workspace. The *master* account must be an admin of the app workspace.

1. Start by creating the workspace. Select **workspaces** > **Create app workspace**. This is where you place the content that your application needs to access.

    ![Create Workspace](media/embed-sample-for-your-organization/embed-sample-for-your-organization-020.png)

2. Give the workspace a name. If the corresponding **Workspace ID** isn't available, edit it to come up with a unique ID. This needs to be the name of the app, too.

    ![Name Workspace](media/embed-sample-for-your-organization/embed-sample-for-your-organization-021.png)

3. You have a few options to set. If you choose **Public**, anyone in your organization can see what’s in the workspace. **Private**, on the other hand, means only members of the workspace can see its contents.

    ![Private/Public](media/embed-sample-for-your-organization/embed-sample-for-your-organization-022.png)

    You can't change the Public/Private setting after you've created the group.

4. You can also choose if members can **edit** or have **view-only** access.

    ![Adding Members](media/embed-sample-for-your-organization/embed-sample-for-your-organization-023.png)

5. Add email addresses of people you want to have access to the workspace, and select **Add**. You can’t add group aliases, just individuals.

6. Decide whether each person is a member or an admin. Admins can edit the workspace itself, including adding other members. Members can edit the content in the workspace unless they have view-only access. Both admins and members can publish the app.

    Now you can view the new workspace. Power BI creates the workspace and opens it. It appears in the list of workspaces in which you’re a member. Because you’re an admin, you can select the ellipsis (…) to go back and make changes to it, adding new members or changing their permissions.

    ![New workspace](media/embed-sample-for-your-organization/embed-sample-for-your-organization-025.png)

### Create and publish your reports

You can create your reports and datasets using Power BI Desktop and then publish those reports to an app workspace. The end user publishing the reports need to have a Power BI Pro license to publish to an app workspace.

1. Download the sample [Blog Demo](https://github.com/Microsoft/powerbi-desktop-samples) from GitHub.

    ![report sample](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026-1.png)

2. Open sample PBIX report in **Power BI Desktop**

   ![PBI desktop report](media/embed-sample-for-your-organization/embed-sample-for-your-organization-027.png)

3. Publish to the **app workspace**

   ![PBI desktop report](media/embed-sample-for-your-organization/embed-sample-for-your-organization-028.png)

    Now you can view the report in the Power BI service online.

   ![PBI desktop report](media/embed-sample-for-your-organization/embed-sample-for-your-organization-029.png)

## Embed your content using the sample application

Follow these steps to start embedding your content using a sample application.

1. Download the [User Owns Data sample](https://github.com/Microsoft/PowerBI-Developer-Samples) from GitHub to get started.  There are 3 different sample applications, one for [reports](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), one for [dashboards](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), and one for [tiles](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app).  We will be reffering to the **reports** application as we discuss the steps below.

    ![User Owns Data application sample](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026.png)

2. Open up the Cloud.config file in the sample application. There are 2 fields you need to fill in to run the application successfully. The **ClientID**, the and the **ClientSecret**.

    ![Cloud Config file](media/embed-sample-for-your-organization/embed-sample-for-your-organization-030.png)

    Fill in the **ClientID** information with the **Application ID** from **Azure**. The **ClientID** is used by the application to identify itself to the users from which you're requesting permissions. To get the **ClientID**, follow these steps:

    Sign into the [Azure portal](https://portal.azure.com).

    ![Azure Portal Main](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    In the left-hand navigation pane, choose **All Services** and select **App Registrations**.

    ![App registration search](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)
    Select the application that you want to get the **ClientID** for.

    ![Choosing App](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    You should see an **Application ID** that is listed as a GUID. Use this **Application ID** as the **clientId** for the application.

    ![ClientID](media/embed-sample-for-your-organization/embed-sample-for-your-organization-007.png)

    Fill in the **ClientSecret** information with the [Application Secret](https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/key-vault) from **Azure**.

    ![ClientSecret](media/embed-sample-for-your-organization/embed-sample-for-your-organization-031.png)

     Fill in the **groupId** information with the **app workspace GUID** from Power BI.

    ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    Fill in the **reportId** information with the **report GUID** from Power BI.

    ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

3. Run the application!

    First select **Run** in **Visual Studio**.

    ![Run the application](media/embed-sample-for-your-organization/embed-sample-for-your-organization-033.png)

    Then select **Get Report**.

    ![Select a content](media/embed-sample-for-your-organization/embed-sample-for-your-organization-034.png)

    Now you can view the report in the sample application.

    ![View application](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

## Embed your content within your application
Even though the steps to embed your content can be done with the [Power BI REST APIs](https://docs.microsoft.com/rest/api/power-bi/), the example codes described in this article are made with the **.NET SDK**.

To integrate a report into a web app, you use the **Power BI REST API**, or the **Power BI C# SDK**, and an Azure Active Directory (AD) authorization **access token** to get a report. Then, you load the report using the same **access token**. The **Power BI Rest API** provides programmatic access to certain **Power BI** resources. For more information, see [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) and the [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript).

## Get a report
To get a **Power BI** report, you use the [Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) operation which gets a list of **Power BI reports**. From the list of reports, you can get a report id.

### Get reports using an access token
With the **access token** you retrieved, you can call the [Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) operation. The [Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) operation returns a list of reports. You can get a single report from the list of reports. Below is a complete **C# method** to get a report.

To make the REST API call, you must include an *Authorization* header in the format of *Bearer {access token}*.

#### Get reports with the REST API

**Default.aspx.cs**

```csharp
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### Get reports using the .NET SDK
You can use the .NET SDK to retrieve a list of reports instead of calling the REST API directly.

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## Load a report using JavaScript
You can use JavaScript to load a report into a div element on your web page.

**Default.aspx**

```javascript
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```javascript
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

## Working with groups (app workspaces)
For embedding a report from a group (app workspace), you will want to get the list of all available reports within a group's dashboard using the following REST API call. To find more information about this REST API call, see [Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports). You will need to have permission in the group for the request to return results.

```HTTPS
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

The above API returns the list of the available reports. Each report has an EmbedUrl property which is already constructed to support group embedding.

```HTTPS
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

For a full sample of using the JavaScript API, you can use the [Playground tool](https://microsoft.github.io/PowerBI-JavaScript/demo). This is a quick way to play with different types of Power BI Embedded samples. You also can get more Information about the JavaScript API by visiting the [PowerBI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) page.

## Move to production

Now that you've completed developing your application, it is time to back your app workspace with dedicated capacity. Dedicated capacity is required to move to production.

### Create a dedicated capacity
By creating a dedicated capacity, you can take advantage of having a dedicated resource for your customer. For workspaces that are not assigned to a dedicated capacity, these need to be in a shared capacity. You can create a dedicated capacity using the [Power BI Embedded dedicated capacity](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity) solution in Azure.

Using embed tokens with PRO licenses are intended for development testing, so the number of embed tokens a Power BI master account can generate is limited. You must purchase a dedicated capacity for embedding in a production environment. There is no limit on how many embed tokens you can generate with a dedicated capacity. Go to [Available Features](https://docs.microsoft.com/rest/api/power-bi/availablefeatures/getavailablefeatures) to check the usage value that indicates the current embedded usage in percentage. The usage amount is based per master account.

### Assign an app workspace to a dedicated capacity

Once dedicated capacity is created, assign the app workspace to the dedicated capacity. To complete this, follow these steps.

1. Within the **Power BI service**, expand workspaces and select the ellipsis for the workspace you're using for embedding your content. Then select **Edit workspaces**.

    ![Edit Workspace](media/embed-sample-for-your-organization/embed-sample-for-your-organization-036.png)

2. Expand **Advanced**, then enable **Dedicated capacity**, then select the dedicated capacity you created. Then select **Save**.

    ![Assign dedicated capacity](media/embed-sample-for-your-organization/embed-sample-for-your-organization-024.png)

For further questions about Power BI Embedded, please visit the [FAQ](embedded-faq.md) page.  If you are having issues with Power Bi Embedded within your application, then please visit the [troubleshoot](embedded-troubleshoot.md) page.

More questions? [Try asking the Power BI Community](http://community.powerbi.com/)