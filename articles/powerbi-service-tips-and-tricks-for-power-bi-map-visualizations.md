﻿<properties
   pageTitle="Tips and Tricks for Power BI Map visualizations"
   description="Tips and Tricks for Power BI Map visualizations"
   services="powerbi"
   documentationCenter=""
   authors="mihart"
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
   ms.date="05/10/2016"
   ms.author="mihart"/>

# Tips and Tricks for Power BI Map visualizations  

Power BI integrates with Bing to provide default map coordinates (a process called geo-coding) so it's easier for you to create maps. Bing uses some algorithms and hints to try to get the right location, but it's a best guess. To increase the likelihood of correct geo-coding, you can use the following tips:

**1. Use Geo Location Terms**

When columns are named based on the geographic designation, it helps Bing guess what you want to display. For example, if you have a field of US state names such as *California* and *Washington*, if the column is not named based on the geographic designation (state, in this case), Bing might return the location of *Washington, DC* instead of Washington State for the word *Washington*. Naming that column *State* will improve the geocoding. The same is true for columns named *Country*, *State*, and *City*.   

**2. Use a comma to add more context to the geo field**

Some designations are ambiguous when considered in the context of multiple countries or regions. You can increase the accuracy of geo-coding by building columns that append multiple fields together and use those for plotting data locations. For example, instead of passing only *Wiltshire*, you can pass *Wiltshire, England* to get a more accurate geo-coding result. 

**3. Use specific Latitude and Longitude**

You can always provide specific latitude and longitude locations. When you do this, you also need to fill the *Location* field when creating your visualizations. Otherwise, the data is aggregated by default, so for example, the latitude and longitude would be paired at the state level, not the city level. Latitude and Longitude fields must be in *Decimal Number* format, which you can set in the data model.

<iframe width="560" height="315" src="https://www.youtube.com/embed/mGkdiZF8GEM" frameborder="0" allowfullscreen></iframe>

## Categorizing geographic fields to hint Bing's geocoding  
In Power BI Desktop, you can ensure fields are correctly geocoded by setting the *Data Category* on the data fields. In Power BI Desktop, select the desired table, go to the **Advanced** ribbon and then set the **Data Category** to **Address**, **City**, **Continent**, **Country/Region**, **Country**, **Postal Code**, **State** or **Province**. These data categories help Bing correctly encode the date. To learn more, see [Data categorization in Power BI Desktop](powerbi-desktop-data-categorization.md).

## Better geocoding with more specific locations  
Sometimes, even setting the data categories for mapping isn't enough for Bing to correctly guess your intent. Within the query, you can build a more specific location like a street address using **Query Editor** in Power BI Desktop.  Use the **Add Column** feature to build a custom column, then build the desired location as follows: 


    = [Field1] & " " & [Field2]

Then use the resulting field in the map visualizations. This approach is very useful for building Street addresses from Shipping Address fields, which are common in data sets. Note that concatenation only works with text fields. If necessary, convert the street number to a *text* data type before using it to build an address.  

## See also

[Power Bi visualizations](powerbi-service-visualizations-for-reports.md)
