<properties
   pageTitle="Power BI permissions"
   description="Power BI permissions"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
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
   ms.date="09/05/2017"
   ms.author="asaxton"/>

# Power BI permissions

## Permission scopes

Power BI permissions give an application the ability to take certain actions on a user's behalf. All permissions must be approved by a user in order to be valid.

|Display Name|Description|Scope Value|
|---|---|---|
|View all Datasets|The app can view all datasets for the signed in user and datasets that the user has access to.|Dataset.Read.All|
|Read and Write all Datasets|The app can view and write to all datasets for the signed in user and datasets that the user has access to.|Dataset.ReadWrite.All|
|Add data to a user's dataset (preview)|Gives an app access to add or delete a user's dataset rows. This permission does not grant the app access to the user's data.|Data.Alter_Any|
|Create content (preview)|App can automatically create content and datasets for a user.|Content.Create|
|View users Groups|The app can view all groups that the signed in user belongs to.|Group.Read|
|View all Groups|The app can view all groups that the signed in user belongs to.|Group.Read.All|
|View all Dashboards (preview)|The app can view all dashboards for the signed in user and dashboards that the user has access to.|Dashboard.Read.All|
|View all Reports (preview)|The app can view all reports for the signed in user and reports that the user has access to. The app can also see the data within the reports as well as its structure.|Report.Read.All|
|Read and write all Reports|The app can view and write to all the reports for the signed in user and any reports that the user has access to. This does not provide rights to create a new report.|Report.ReadWrite.All|

An application can request permissions when it first attempts to log in to a user's page by passing in the requested permissions in the scope parameter of the call. If the permissions are granted, an access token will be returned to the app which can be used on future API calls. The access can only be used by a specific application.

> [AZURE.NOTE] The Power BI APIs still refer to app workspaces as groups. Any references to groups mean that you are working with app workspaces.

## Requesting Permissions

While you can call the API to authenticate with a username and password, in order to take actions on behalf of another user, they will need to request permissions that the user then approves and then send the resulting access token on all future calls. For this process, we will follow the standard [OAuth 2.0](http://oauth.net/2/) protocol. While the actual implementation may vary, the OAuth flow for Power BI has the following elements:

- **Login UI** - This is a UI that the developer can evoke to request permissions. It would require the user to log in if not already. The user would also need to approve the permissions that the application is requesting. The login window will post back either an access code or an error message to a redirect URL that is supplied.
	- A standard redirect URL should be supplied by Power BI for use by native applications.
- **Authorization Code** - Authorization Codes are returned to web applications after login via URL parameters in the redirect URL. Since they are in parameters there is some security risk. Web applications will have to exchange the authorization code for an Authorization Token
- **Authorization Token** - Are used to authenticate API calls on another user's behalf. They will be scoped to a specific application. Tokens have a set lifespan and when they expire they will need to be refreshed.
- **Refresh Token** - When tokens expire there will be a process of refreshing them.

More questions? [Try asking the Power BI Community](http://community.powerbi.com/)
