---
title: Troubleshooting how to develop Power BI custom visuals
description: This article discusses some common issues you may encounter when developing or creating a custom Power BI visual.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/06/2018
---

# Troubleshooting your Power BI custom visuals

**Pbiviz command not found (or similar errors)**

When you run `pbiviz` in your terminal's command line, you should see the help screen. If not, then it is not installed correctly. Make sure you have at least the 4.0 version of NodeJS installed.

**Can't find the debug visual in the Visualizations tab**

The debug visual looks like a prompt icon within the **Visualizations** tab.

![Visual selection](media/service-custom-visuals-getting-started-with-developer-tools/powerbi-developer-visual-selection.png)

If you don't see it, make sure you have enabled it within the Power BI settings.

> [!NOTE]
> The debug visual is currently only available in the Power BI service and not in Power BI Desktop or the mobile app. The packaged visual will still work everywhere.

**Can't contact visual server**

Run the visual server with the command `pbiviz start` in your terminal's command line from the root of your visual project. If the server is running, it is likely that your SSL certificates weren't installed correctly.