<properties
   pageTitle="How to find your report server product key"
   description="Learn how you can find your Power BI Report Server product key to install your server in a production environment."
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="kfile"
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
   ms.date="11/01/2017"
   ms.author="asaxton"/>

# How to find your report server product key

Learn how you can find your Power BI Report Server product key to install your server in a production environment.

<iframe width="640" height="360" src="https://www.youtube.com/embed/6CQnf-NGtpU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

You downloaded Power BI Report Server, and you have a SQL Server Enterprise Software Assurance agreement. Or, you purchased Power BI Premium. You want to install the server in a production environment, but you need a product key in order to do that. Where is the product key? 

The product key will be in one of two places depending on what you purchased.

## Purchased Power BI Premium

If you have purchased Power BI Premium, within the **Capacity settings** tab of the Power BI admin portal, you will have access to your Power BI Report Server product key. This will only be available for Global Admins or users assigned the Power BI service administrator role.

![Power BI Report Server key within Premium settings](media/reportserver-find-product-key/pbirs-product-key.png)

Selecting **Power BI Report Server key** will display a dialog contain your product key. You can copy it and use it with the installation.

![Power BI Report Server product key](media/reportserver-find-product-key/pbirs-product-key-dialog.png)

## Purchased Software Assurance agreeemnt

If you have a SQL Server Enterprise SA agreement, you can get your product key from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/). Look under the latest service pack, for the latest version of SQL Server. If you don't see it there, look under the RTM release of the latest SQL Server version.

> [AZURE.NOTE] You need to look under the download section. Not the keys section.

![](media/reportserver-find-product-key/vlsc-download.png "Volume Licensing Service Center")

## Next steps

[Quickstart: Install Power BI Report Server](reportserver-quickstart-install-report-server.md)  
[Install Power BI Desktop optimized for Power BI Report Server](reportserver-install-powerbi-desktop.md)  
[Install Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

More questions? [Try asking the Power BI Community](https://community.powerbi.com/)