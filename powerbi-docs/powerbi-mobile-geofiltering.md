---
title: Filter report by geographic location in a Power BI mobile app
description: Learn how you can filter a report by your geographic location in the Microsoft Power BI mobile apps, if the report owner set geographic tags.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: erikre
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''

ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/13/2017
ms.author: maggies

---
# Filter a report by geographic location in the Power BI mobile apps
Applies to:

| ![iPhone](media/powerbi-mobile-geofiltering/iphone-logo-50-px.png) | ![iPad](media/powerbi-mobile-geofiltering/ipad-logo-50-px.png) | ![Android phone](media/powerbi-mobile-geofiltering/android-phone-logo-50-px.png) | ![Android tablet](media/powerbi-mobile-geofiltering/android-tablet-logo-50-px.png) | ![Android tablet](media/powerbi-mobile-geofiltering/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhones |iPads |Android phones |Android tablets |Windows 10 phones |

When you look at a Power BI report on your mobile device, do you see a little pushpin icon in the upper-right corner? If so, then you can filter that report based on your geographic location.

> [!NOTE]
> You can only filter by location if the geographic names in the report are in English&#150;for example, "New York City" or "Germany". Windows 10 tablets and PCs don't support geographic filtering, but Windows 10 phones do.
> 
> 

## Filter your report by your geographic location
1. Open a report in the Power BI mobile app on your mobile device.
2. If the report has geographic data, you see a message asking to allow Power BI to access your location. Click **Allow**, the tap **Allow** again.
3. Tap the push pin ![Push pin icon](media/powerbi-mobile-geofiltering/power-bi-mobile-geo-icon.png). You can filter on city, state/province, or country/region, depending on the data in the report. The filter only lists options that match your current location.
   
    ![Push pin filter](media/powerbi-mobile-geofiltering/power-bi-mobile-geo-map-set-filter.png)

## Why don't I see location tags on a report?
All three of these conditions need to be true, for you to see location tags. 

* The person who created the report in Power BI Desktop [categorized geographical data](powerbi-desktop-mobile-geofiltering.md) for at least one column, such as City, State, or Country/Region.
* You are in one of the locations that has data in that column.
* You're using one of these mobile devices:
  * iOS (iPad, iPhone, iPod).
  * Android phone or tablet.
  * Windows 10 phone (other Windows 10 devices such as PCs and tablets don't support geographic filtering).

Read more about [setting up geographic filtering](powerbi-desktop-mobile-geofiltering.md) in Power BI Desktop.

### Next steps
* [Connect to Power BI data from the real world](powerbi-mobile-data-in-real-world-context.md) with the mobile apps
* [Data categorization in Power BI Desktop](desktop-data-categorization.md) 
* Questions? [Try asking the Power BI Community](http://community.powerbi.com/)

