---
title: Use SSO (single sign-on) from Power BI to on-premises data sources
description: Configure your gateway to enable SSO from Power BI to on-premises data sources
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2018
LocalizationGroup: Gateways
---

# Overview of single sign on (SSO) in Power BI gateways

You can get seamless single sign-on connectivity, enabling Power BI reports and dashboards to update from on-premises data, by configuring your On-premises data gateway with Kerberos. The On-premises data gateway facilitates single sign-on (SSO) using DirectQuery, which it uses to connect to on-premises data sources.

The following data sources are currently supported, all based on [Kerberos Constrained Delegation](https://technet.microsoft.com/library/jj553400.aspx):

* SQL Server
* SAP HANA
* Teradata
* Spark

When a user interacts with a DirectQuery report in the Power BI Service, each cross-filter, slice, sorting, and report editing operation can result in queries executing live against the underlying on-premises data source.  When single sign-on is configured for the data source, queries execute under the identity of the user interacting with Power BI (that is, through the web experience or Power BI mobile apps). Thereby, each user sees precisely the data for which they have permissions in the underlying data source – with single sign-on configured, there is no shared data caching across different users.

## Running a query with SSO - steps that occur

A query that runs with SSO consists of three steps, as shown in the following diagram.

![](media/service-gateway-sso-overview/kerberos-sso-on-prem_01.png)

> [!NOTE]
> SSO for Oracle is not enabled yet, but is under development and coming soon.

Here are additional details about those steps:

1. For each query, the **Power BI service** includes the *user principal name* (UPN) when sending a query request to the configured gateway.
2. The gateway needs to map the Azure Active Directory UPN to a local Active Directory identity.

   a.  If AAD DirSync (also known as *AAD Connect*) is configured, then the mapping works automatically in the gateway.

   b.  Otherwise, the gateway can look up and map the Azure AD UPN to a local user by performing a lookup against the local Active Directory domain.
3. The gateway service process impersonates the mapped local user, opens the connection to the underlying database and sends the query. The gateway does not need to be installed on the same machine as the database.

## Next steps

For more information about the **On-premises data gateway** and **DirectQuery**, check out the following resources:

* [On-premises data gateway](service-gateway-onprem.md)
* [DirectQuery in Power BI](desktop-directquery-about.md)
* [Data sources supported by DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery and SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery and SAP HANA](desktop-directquery-sap-hana.md)