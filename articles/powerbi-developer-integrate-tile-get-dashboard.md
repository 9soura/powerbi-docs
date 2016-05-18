<properties
   pageTitle="Get a Power BI dashboard"
   description="Walkthrough to Integrate a tile into an app - Get a Power BI dashboard"
   services="powerbi"
   documentationCenter=""
   authors="dvana"
   manager="mblythe"
   editor=""
   tags=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="05/17/2016"
   ms.author="derrickv"/>

# Step 2: Get a Power BI dashboard

## Introduction

In this step of the [Integrate a tile into an app walkthrough](powerbi-developer-integrate-tile.md), you use the **Power BI** API to get a dashboard. After you get a dashboard, you can get a **Power BI** tile.

![](media\powerbi-developer-integrate-tile\integrate-tile-get-dashboard.png)

To get a **Power BI** dashboard, you use the [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) operation which gets a list of **Power BI** dashboards. From the list of dashboards, you can get a dashboard id. Once you have a dashboard id, you can get a **Power BI** tile.

Before you can call the [Get Dashboards]() operation, or any other **Power BI** operation, you need to get an Azure Active Directory **authentication access token** (access token). An **access token** is used to allow your app access to certain **Power BI** resources, such as dashboards and tiles. To learn more about Azure Active Directory **access token** flow, see [Azure AD Authorization Code Grant Flow](https://msdn.microsoft.com/library/azure/dn645542.aspx). The next section shows you how to get an **access token** in a web app.

<a name="get-token"/>
## Get an authentication access token

Here's how to get an authentication access token to call a **Power BI** operation.

-	**Step 1:** [Get an authorization code from Azure AD](#auth-code)
-	**Step 2:** [Get an access token from authorization code](#access-token)

<a name="auth-code"/>
### Step 1: Get an authorization code from Azure AD

The first step to get an **access token** is to get an authorization code from **Azure AD**. To do this, you construct a query string with the following properties, and redirect to **Azure AD**.


**Authorization code query string**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code.
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
    //You get the client id when you register your Azure app.
    {"client_id", Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    //The resource uri is hard-coded for sample purposes
    {"resource", "https://analysis.windows.net/powerbi/api"},

    //After app authenticates, Azure AD will redirect back to the web app. In this sample, Azure AD redirects back
    //to Default page (Default.aspx).
    { "redirect_uri", Settings.Default.RedirectUri}
};
```

After you construct a query string, you redirect to **Azure AD** to get an **authorization code**.  Below is a complete C# method to construct an **authorization code** query string, and redirect to **Azure AD**. In the next step, you get an **access token** using the **authorization code**.

**Get authorization code**

```
public void GetAuthorizationCode()
{
    //NOTE: Values are hard-coded for sample purposes.
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code.
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
        //You get the client id when you register your Azure app.
        {"client_id", Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        //The resource uri is hard-coded for sample purposes
        {"resource", "https://analysis.windows.net/powerbi/api"},

        //After app authenticates, Azure AD will redirect back to the web app. In this sample, Azure AD redirects back
        //to Default page (Default.aspx).
        { "redirect_uri", Settings.Default.RedirectUri}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect to Azure AD Authority
    //  Authority Uri is an Azure resource that takes a client id and client secret to get an Access token
    //  QueryString contains
    //      response_type of "code"
    //      client_id that identifies your app in Azure AD
    //      resource which is the Power BI API resource to be authorized
    //      redirect_uri which is the uri that Azure AD will redirect back to after it authenticates

    //Redirect to Azure AD to get an authorization code
    Response.Redirect(String.Format("https://login.windows.net/common/oauth2/authorize?{0}", queryString));
}
```

<a name="access-token"/>
### Step 2: Get an access token from authorization code

In step 1 to get an authentication access token, you get an **authorization code** from Azure AD. Once **Azure AD** redirects back to your web app with an **authorization code**, you use the **authorization code** to get an access token. Below is a C# method to get an **access token**. In the next section, you get a **dashboard** using an **access token**.

**Get access token**

```
public string GetAccessToken(string authorizationCode, string clientID, string clientSecret, string redirectUri)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    //Note: If you use a redirect back to Default, as in this sample, you need to add a forward slash
    //such as http://localhost:13526/

    // Get auth token from auth code       
    TokenCache TC = new TokenCache();

    //Values are hard-coded for sample purposes
    string authority = "https://login.windows.net/common/oauth2/authorize";
    AuthenticationContext AC = new AuthenticationContext(authority, TC);
    ClientCredential cc = new ClientCredential(clientID, clientSecret);

    //Set token from authentication result
    return AC.AcquireTokenByAuthorizationCode(
        authorizationCode,
        new Uri(redirectUri), cc).AccessToken;
}
```

## Get dashboard using access token

Now that you have an **access token**, you can call the [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) operation. The [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) operation returns a list of dashboards. You can get a dashboard from the list of dashboards. Below is a complete C# method to get a dashboard. Once you have a **dashboard**, you can get a **tile**. See [Step 3: Get a Power BI tile]( powerbi-developer-integrate-tile-get-tile.md).

**Get dashboard**

```
//Get a dashbaord id. In this sample, you get the first tile.
protected string GetDashboard(int index)
{
    string dashboardId = string.Empty;

    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIDashboards dashboards = JsonConvert.DeserializeObject<PBIDashboards>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            dashboardId = dashboards.value[index].id;
        }
    }

    return dashboardId;
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
}
```

[Next Step >](powerbi-developer-integrate-tile-get-tile.md)

## See also

-	[Sign up for Power BI](powerbi-admin-free-with-custom-azure-directory.md)
-	[Integrate a tile into an app walkthrough](powerbi-developer-integrate-tile.md)
-	[Integrate a tile sample](https://github.com/Microsoft/PowerBI-CSharp/tree/master/samples/webforms/integrate-tile-web-app)
-	[Configure the integrate a tile sample](powerbi-developer-integrate-tile-register.md#configure-sample)
-	[Azure AD Authorization Code Grant Flow](https://msdn.microsoft.com/library/azure/dn645542.aspx)
-	[Get Dashboards operation](https://msdn.microsoft.com/library/mt465739.aspx)
-	[Step 3: Get a Power BI tile](powerbi-developer-integrate-tile-get-tile.md)
