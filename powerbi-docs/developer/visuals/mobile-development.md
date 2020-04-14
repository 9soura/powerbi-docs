---
title:  Mobile Development
description:  How to create mobile-friendly Custom Visual
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 03/12/2019
---
# How to create a mobile-friendly Custom Visual
Mobile consumption has a major role in Power BI with one of its strengths in staying connected to your data anytime, anywhere.

As a developer creating Custom Visuals, the unique constraints of each mobile device must be addressed to reach the most users and provide them the best possible experience.

Use the [Power BI app for Windows, iOS, and Android](/power-bi/consumer/mobile/mobile-apps-for-mobile-devices) to give your business users a 360° view of their data on the go - all at the touch of their fingertips.

## Requirements

The following requirements are essential for mobile-friendly visual development:

- Render

  Custom Visuals need to render on all supported mobile devices, including supported browsers and applications, with no errors in reports, dashboards, or when running in **Focus** mode. 

- Interactive

  Interactive functionality must be provided same as for desktop devices, and all events handled on desktop browsers must be supported or have analogous event handlers provided specific to mobile devices.
  
  For example, basic navigation and the selection of data points should be implementated same as provided for desktop browsers. If a visual supports multi-select using **Ctrl**, the developer needs to consider adding a similar event handler for mobile devices.

  The following provides a list of corresponding events on mobile devices:

  | Mouse event name | Touch event name |
  |:----------------:|:----------------:|
  | `click` | `click` |
  | `mousemove` | `touchmove` |
  | `mousedown` | `touchstart` |
  | `mouseup` | `touchend` |
  | `dblclick` | use external library |
  | `contextmenu` | use external library |
  | `mouseover` | `touchmove` |
  | `mouseout` | `touchmove` (or external library) |
  | `wheel` | `NaN` |

  > [!NOTE]
  > Not all mobile or touch screen devices support mouse (or *mouse* prefixed) events. In such cases, handle both *mouse* and *touch* events at the same time.

## Optional
The following are considered optional and used to create a better end-user experience.

- Render

  To support smaller visual sizes, try adding format options the user can change to adjust the size of each element, such as labels, for use in reports and dashboards. This allows users to customize a visual specifically for their mobile device. 
  
  These same settings can also be applied to the visuals in desktop browsers, and if needed, be overridden to adapt the visual to smaller screens.

  > [!NOTE]
  > To optimize a visual in **Focus** mode, both portrait and landscape screen size orientations need consideration, see [Display content in Focus mode](/power-bi/consumer/end-user-focus).

- Interactive

  Consider the addition of mobile-specific event handlers, like dragging and scrolling.

- Failover

  A visual should show a descriptive error if it cannot render on the mobile device for any reason.

## Supported browsers and devices
The custom visual must render on all devices supporting Power BI Apps, for more information see [supported browsers for Power BI](/power-bi/power-bi-browsers) and [Power BI mobile apps](/power-bi/consumer/mobile/mobile-apps-for-mobile-devices).

When testing against the latest models of Windows, iOS, and Android devices, the developer needs to consider most of these quality aspects.

To get started, see [Tutorial: Developing a Power BI visual](/power-bi/developer/visuals/custom-visual-develop-tutorial).
