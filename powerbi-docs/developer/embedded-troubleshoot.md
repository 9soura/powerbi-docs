---
title: Troubleshooting your embedded application
description: This article discusses some common issues you may encounter when embedding content from Power BI.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 07/03/2018
ms.author: maghan
---
# Troubleshooting your embedded application

This article discusses some common issues you may encounter when embedding content from Power BI.

## Tools for troubleshooting

### Fiddler Trace

[Fiddler](http://www.telerik.com/fiddler) is a free tool from Telerik that monitors HTTP traffic.  You can see the back and forth with the Power BI APIs from the client machine. This may show errors and other related information.

![Fiddler trace](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### F12 in Browser for front end debugging

F12 will launch the developer window within your browser. This provides the ability to look at network traffic and other information.

![F12 Browser debugging](media/embedded-troubleshoot/browser-f12.png)

### Extracting error details from Power BI response

This code snippet shows how to extract the error details from HTTP exception:

```
public static string GetExceptionText(this HttpOperationException exc)
{
    var errorText = string.Format("Request: {0}\r\nStatus: {1} ({2})\r\nResponse: {3}",
    exc.Request.Content, exc.Response.StatusCode, (int)exc.Response.StatusCode, exc.Response.Content);
    if (exc.Response.Headers.ContainsKey("RequestId"))
    {
        var requestId = exc.Response.Headers["RequestId"].FirstOrDefault();
        errorText += string.Format("\r\nRequestId: {0}", requestId);
    }

    return errorText;
}
```
We recommend logging the request ids (and error details for troubleshooting).
Please provide the request id when approaching Microsoft support.

## App registration

**App registration failure**

Error messages within the Azure portal or the Power BI app registration page will mention insufficient privileges. In order to register an application, you must be an admin in the Azure AD tenant or application registrations must be enabled for non-admin users.

**Power BI Service does not appear in Azure portal when registering a new App**

At least one user must be signed up for Power BI. If you do not see **Power BI Service** listed within the API list, no user is signed up for Power BI.

## REST API

**API call returning 401**

A fiddler capture may be required to investigate further. The required permission scope may be missing for the registered application within Azure AD. Verify the required scope is present within the app registration for Azure AD within the Azure portal.

**API call returning 403**

A fiddler capture may be required to investigate further. There could be several reason for a 403 error.

* The user have exceeded the amount of embed token that can be generated on a shared capacity. You need to purchase Azure capacities to generate embed tokens, and assign the workspace to that capacity. See [Create Power BI Embedded capacity in the Azure portal](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity).
* The Azure AD auth token expired.
* The authenticated user is not a member of the group (app workspace).
* The authenticated user is not an admin of the group (app workspace).
* The authorization header may not be listed correctly. Make sure there are no typos.

The backend of the application may need to refresh the auth token before calling GenerateToken.

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

## Authentication

### Authentication failed with AADSTS70002 or AADSTS50053

**(AADSTS70002: Error validating credentials. AADSTS50053: You've tried to sign in too many times with an incorrect user ID or password)**

If you are using Power BI Embedded and utilizing Azure AD Direct Authentication, and you are receiving messages logging in such as ***error:unauthorized_client,error_description:AADSTS70002: Error validating credentials. AADSTS50053: You've tried to sign in too many times with an incorrect user ID or password***, that is because direct authentication has been turned off as of 6/14/2018.

We recommend to use the [Azure AD Conditional Access](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/07/azure-ad-conditional-access-support-for-blocking-legacy-auth-is-in-public-preview/) support for blocking legacy authentication or use [Azure AD Directory Pass-through Authentication](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).

However, there is a way to turn this back on using an [Azure AD Policy](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/configure-authentication-for-federated-users-portal#enable-direct-authentication-for-legacy-applications) that can either be scoped to the organization or a [service principal](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-application-objects#service-principal-object).

**_We recommend you enable this only as a per-app basis and only as needed for a workaround._**

To create this policy, you need to be a **Global Administrator** for the directory where you’re creating the policy and assigning. Here is a sample script for creating the policy and assigning it to the SP for this application:

1. Install the [Azure AD Preview PowerShell Module](https://docs.microsoft.com/en-us/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).

2. Run the following powershell commands line-by-line (making sure the variable $sp doesn’t have more than 1 application as a result).

```powershell
Connect-AzureAD
```

```powershell
$sp = Get-AzureADServicePrincipal -SearchString "Name_Of_Application"
```

```powershell
$policy = New-AzureADPolicy -Definition @("{`"HomeRealmDiscoveryPolicy`":{`"AllowCloudPasswordValidation`":true}}") -DisplayName EnableDirectAuth -Type HomeRealmDiscoveryPolicy -IsOrganizationDefault $false
```

```powershell
Add-AzureADServicePrincipalPolicy -Id $sp.ObjectId -RefObjectId $policy.Id 
```

After assigning the policy, please wait approximately 15-20 seconds for propagation before testing.

**Generate token fails when providing effective identity**

GenerateToken can fail, with effective identity supplied, for a few different reasons.

* Dataset does not support effective identity
* Username was not provided
* Role was not provided
* DatasetId was not provided
* User doesn't have the correct permissions

To verify which it is, try the following.

* Execute [get dataset](https://docs.microsoft.com/rest/api/power-bi/datasets). Is the property IsEffectiveIdentityRequired true?
* Username is mandatory for any EffectiveIdentity.
* If IsEffectiveIdentityRolesRequired is true, Role is required.
* DatasetId is mandatory for any EffectiveIdentity.
* For Analysis Services, the master user has to be a gateway admin.

### AADSTS90094: The grant requires admin permission

**_Symptoms:_**
When a non-admin user attempts to sign-in to an application for the first and grant consent she gets the following error:
* ConsentTest needs permission to access resources in your organization that only an admin can grant. Please ask an admin to grant permission to this app before you can use it.
* AADSTS90094: The grant requires admin permission.

    ![Consent Test](media/embedded-troubleshoot/consent-test-01.png)

An admin user can sign-in and grant consent successfully.

**_Root cause:_**
User consent is disabled for the tenant.

**_Fix:_**

Several fixes are possible:

*Enable user consent for the entire tenant (all users, all applications)*
1. In Azure Portal navigate to "Azure Active Directory" => "Users and groups" => "User settings"
2. Enable the "Users can consent to apps accessing company data on their behalf" setting and save the changes

    ![Consent Test Fix](media/embedded-troubleshoot/consent-test-02.png)

*Grant permissions by an admin*
Grant permissions to the application by an admin - either for the entire tenant or for a specific user.

## Data sources

**ISV wants to have different credentials for the same data source**

A data source can have a single set of credentials for one master user. If you need to use different credentials, create additional master users. Then, assign the different credentials in each of the master users context, and embed using the Azure AD token of that user.

## Content rendering

**Rendering, or consumption, of embedded content fails or times out**

Make sure the embed token did not expire. Make sure you are checking the embed token expiration and refreshing it. For more information, see [Refresh token using JavaScript SDK](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example).

**Report or dashboard does not load**

If the user is unable to see the report or dashboard, make sure the report or dashboard loads correctly within powerbi.com. The report or dashboard will not work within your application if it doesn't load within powerbi.com.

**Report or dashboard is performing slowly**

Open the file from Power BI Desktop, or within powerbi.com, and verify that performance is acceptable to rule out issues with your application or the embedding apis.

## Onboarding experience tool for embedding

You can go through the [Onboarding experience tool](https://aka.ms/embedsetup) to quickly download a sample application. Then you can compare your application to the sample.

### Prerequisites

Verify that you have all the proper prerequisites before using the Onboarding experience tool. You need a **Power BI Pro** account and a **Microsoft Azure** subscription.

* If you're not signed up for **Power BI Pro**, [sign up for a free trial](https://powerbi.microsoft.com/en-us/pricing/) before you begin.
* If you don’t have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.
* You need to have your own [Azure Active Directory tenant ](create-an-azure-active-directory-tenant.md) setup.
* You need [Visual Studio](https://www.visualstudio.com/) installed (version 2013 or later).

### Common Issues

Some common issues you might encounter when testing with the Onboarding experience tool are:

#### Using the Embed for your customers sample application

If you are working with the **Embed for your customers** experience, save and unzip the *PowerBI-Developer-Samples.zip* file. Then open the *PowerBI-Developer-Samples-master\App Owns Data* folder and run the *PowerBIEmbedded_AppOwnsData.sln* file.

When selecting **Grant permissions** (the Grant permissions step), you get the following error:

    AADSTS70001: Application with identifier <client ID> was not found in the directory <directory ID>

The solution is to close the popup, wait a few seconds and try again. You might need to repeat this action a few times. A time interval causes the issue from completing the application registration process to when it is available to external APIs.

The following error message appears when running the sample app:

    Password is empty. Please fill password of Power BI username in web.config.

This error occurs because the only value that is not being injected into the sample application is your user password. Open the Web.config file in the solution and fill the pbiPassword field with your user's password.

#### Using the Embed for your organization sample application

If you are working with the **Embed for your organization** experience, save and unzip the *PowerBI-Developer-Samples.zip* file. Then open the *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* folder and run the *pbi-saas-embed-report.sln* file.

When you run the **Embed for your organization** sample app, you get the following error:

    AADSTS50011: The reply URL specified in the request does not match the reply URLs configured for the application: <client ID>

This is because the redirect URL specified for the web-server application is different from the sample's URL. If you want to register the sample application, then use `http://localhost:13526/` as the redirect URL.

If you would like to edit the registered application, then learn how to edit the [AAD registered application](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application), so the application can provide access to the web APIs.

If you would like to edit your Power BI user profile or data, then learn how to edit your [Power BI data](https://docs.microsoft.com/en-us/power-bi/service-basic-concepts).

For more information, please see [Power BI Embedded FAQ](embedded-faq.md).

More questions? [Try the Power BI Community](http://community.powerbi.com/)