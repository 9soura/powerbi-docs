<properties
   pageTitle="Changelog for Power BI Report Server"
   description="Changelog, Power BI Report Server "
   services="powerbi"
   documentationCenter=""
   authors="jaimeta"
   manager="jonhp"
   backup="asaxton"
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
   ms.date="07/11/2017"
   ms.author="jaimeta"/>

# Changelog for Power BI Report Server

This change log is for Power BI Report Server.

For detailed posts about what’s new and changed, please visit the SSDT Team blog

## June 2017 (Build 14.0.600.301)

*Released: July 11, 2017*

### What's new?

- Machine key information now stored within the rsreportserver.config. For more information, see [How to install custom security extensions](https://docs.microsoft.com/sql/reporting-services/extensions/security-extension/how-to-install-custom-security-extensions#machine-keys).

### Bug Fixes

- The {{UserId}} tag resolves to the stored credentials instead of the user executing the report in Power BI Reports
- Some images fail to render in Power BI Report Server reports
- Unable to change the name of a Power BI Report in the Power BI Report Server
- Unable to load Custom Visuals in the Power BI mobile application (it requires reinstall of the mobile app to clear up the local cache)

## June 2017 (Build 14.0.600.271)

*Released: June 12, 2017*

- Power BI Server initial release

## Next steps

[User handbook](reportserver-user-handbook-overview.md)  
[Administrator handbook](reportserver-admin-handbook-overview.md)  
[Quickstart: Install Power BI Report Server](reportserver-quickstart-install-report-server.md)  
[Install Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

More questions? [Try asking the Power BI Community](https://community.powerbi.com/)
