---
title: Use the numeric range slicer in Power BI Desktop
description: Learn how to use a slicer for constraining to numeric ranges in Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''

ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/07/2018
ms.author: davidi

LocalizationGroup: Create reports
---
# Use the numeric range slicer in Power BI Desktop
With the **numeric range slicer**, you can apply all sorts of filters to any numeric column in your data model. You can choose to filter **between** numbers, **less than or equal** to a number, or **greater than or equal** to a number. While this may sound straightforward, it's a very powerful way to filter your data.

![Visual with numeric range slicer](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## Using the numeric range slicer
You can use the numeric range slicer just like any other slicer. Simply create a **slicer** visual for your report, and then select a numeric value for the **Field** value. In the following image, the *LineTotal* field is selected.

![Create a numeric range slicer](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Select the down-arrow link in the upper-right corner of the **numeric range slicer** and a menu appears.

![Numeric range slicer menu](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

For the numeric range, you can select from the following three selections:

* Between
* Less than or equal to
* Greater than or equal to

When you select **Between** from the menu, a slider appears and you can filter for numeric values that fall between the numbers. In addition to using the slider bar itself, you can click in either box and type in the values. This is convenient when you want to slice on specific numbers, yet the granularity of moving the slicer bar makes it difficult to land exactly on that number.

In the following image, the report page is filtered for *LineTotal* values that range between 2500.00 and 6000.00.

![Numeric range slicer with Between](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

When we select **Less than or equal to**, the left (lower value) handle of the slider bar disappears, and we can adjust only  the upper bound of the slider bar. In the following image, we set the slider bar maximum to 5928.19.

![Numeric range slicer with Less than](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Lastly, if we select **Greater than or equal to**, then the right (highest value) slider bar handle disappears, and we can adjust the lower value, as seen in the following image. Now only items with a *LineTotal* greater than or equal to 4902.99 are displayed in the visuals on the report page.

![Numeric range slicer with Greater than](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## Snap to whole numbers with the numeric range slicer

A numeric range slicer will snap to whole numbers, unless it is a decimal range. This lets your slicer to cleanly align who whole numbers. 


## Limitations and considerations
The following limitations and considerations currently apply to the **numeric range slicer**

* The **numeric range slicer** currently filters every underlying row in the data, not any aggregated value. For example, if a *Sales Amount* field is used, each transaction based on *Sales Amount* would be filtered upon, not the sum of *Sales Amount* for each data point of a visual.
* It does not currently work with Measures.
