---
title: Capacity in Power BI embedded analytics
description: Browse a list of frequently asked questions and answers about Power BI Embedded.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 12/04/2019 
---

# Capacity in Power BI embedded analytics

Embedded analytics requires a capacity for publishing embedded Power BI content.

Capacity is a dedicated set of resources reserved for exclusive use. It enables you to publish dashboards, reports, and datasets to users, without having to purchase per-user licenses. It also offers dependable, consistent performance for your content.

>[!NOTE]
>For publishing, you'll need one Power BI Pro account.

## What is embedded analytics?

Power BI embedded analytics includes two solutions:
* *Power BI Embedded*  - Azure offering
* Embedding Power BI as part of *Power BI Premium*  - Office offering

### Power BI Embedded

Power BI Embedded is for ISVs and developers who want to embed visuals into their applications.

Applications using Power BI Embedded allow users to consume content stored on Power BI Embedded capacity, including anyone inside or outside the organization.

### Power BI Premium

[Power BI Premium](../service-premium-what-is.md) is geared toward enterprises who want a complete BI solution that provides a single view of its organization, partners, customers, and suppliers.

Power BI Premium is a SaaS product that allows users to consume content through mobile apps, internally developed apps, or at the Power BI portal (Power BI service).

Power BI premium offers two SKUs, *P* and *EM*. To understand the difference between these to SKUs, refer to [subscriptions and licensing](../service-premium-what-is.md#subscriptions-and-licensing).

## Capacity recommendations

When you buy a Power BI Embedded capacity, you have to use an A SKU.

When you buy a Power BI Premium capacity, you can choose between EM and P SKUs.

The table below lists Microsoft's capacity recommendations. The recommendations depend on the type of customer and solution you wish to deploy. The table also lists payment and usage considerations per capacity.

</br>
<table>
<tbody>
<tr>
<td></td>
<td style="text-align: center;"><p><strong>Power BI Embedded</strong></p></td>
<td style="text-align: center;" colspan="2"><p><strong>Power BI Premium</strong></p></td>
</tr>
<tr>
<td><p><strong>Offer</strong></p></td>
<td style="text-align: center;"><p>Azure</p></td>
<td style="text-align: center;" colspan="2"><p>Office</p></td>
</tr>
<tr>
<td><p><strong>SKU</strong></p></td>
<td style="text-align: center;"><p>A</p></td>
<td style="text-align: center;"><p>EM</p></td>
<td style="text-align: center;"><p>P</p></td>
</tr>
<tr>
<td><p><strong>Billing</strong></td>
<td style="text-align: center;">Hourly</td>
<td style="text-align: center;">Monthly</td>
<td style="text-align: center;">Monthly</td>
</tr>
<tr>
<td><p><strong>Commitment</strong></td>
<td style="text-align: center;">None</td>
<td style="text-align: center;">Yearly</td>
<td style="text-align: center;">Monthly or yearly</td>
</tr>
<tr>
<td valign="top"><p><strong>Usage</strong></td>
<td style="text-align: center;">Azure resources can be:</br>- Scaled up or down</br>- Paused and resumed
</td>
<td style="text-align: center;">Embed online, and in</br> Microsoft applications</td>
<td style="text-align: center;">Embed in apps, and</br> in Power BI service</td>
</tr>
</tbody>
</table>

>[!NOTE]
>Customers have no restriction on which product to buy.

## Which SKU should I use?

This table provides a summary of features, the capacity they require, and the specific SKU that is required for each one. 

</br>
<table>
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<tbody>
<tr>
<td style="text-align: center"; colspan="2"><p><b>Feature</b></p></td>
<td style="text-align: center">
<p><b>Power BI Embedded</b></p>
</td>
<td style="text-align: center"; colspan="2">
<p><b>Power BI Premium</b></p>
</td>
</tr>
<tr>
<td><p><em>What is consumed?</em><p></td>
<td><p><em>What  is consuming?</em><p></td>
<td style="text-align: center"><p><em>A SKUs</br>(Azure)</em></p></td>
<td style="text-align: center"><p><em>EM SKUs</br>(Office)</em></p></td>
<td style="text-align: center"><p><em>P SKUs</br>(Office)</em></p></td>
</tr>
<tr>
<td>Embed artifacts from a Power BI workspace</td>
<td>
</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="2">Power BI reports</td>
<td>An embedded application for your organization</br>(user owns data)</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>An embedded application for your customers</br>(app owns data)</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="3">Power BI content<br>(with a free Power BI license)</td>
<td>Power BI service</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Power BI mobile</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>MS Office apps</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
</tbody>
</table>
