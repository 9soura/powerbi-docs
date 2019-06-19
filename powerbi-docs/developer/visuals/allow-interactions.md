---
title: Allow interactions
description:
author: shaym83
ms.author: shaym
manager: AviSander
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
---

# Allow interactions

Visuals can query the value of the 'allowInteractions' flag, that indicates whether the visual should allow visual interactions.
For example, visuals should be interactive during report viewing or editing, but not interactive when viewed in a dashboard.
These interactions are click, pan, zoom, selection, etc.
Note, that tooltips are expected to be enabled in all scenarios, whatever of this flag.

## Getting the 'allowInteractions' value

The 'allowInteractions' flag is passed as a boolean during the initialization of the visual, as a member of the IVisualHost interface.

In any Power BI scenario that requires the visuals not to be interactive (e.g. Dashboard tiles) - 'allowInteractions' flag will be set to false.
Otherwise (for example, Report), 'allowInteractions' will be set to true.
You can find the full sample code at [SampleBarChart with allowInteractions](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001)

```typescript
   ...
   let allowInteractions = options.host.allowInteractions;
   bars.on('click', function(d) {
       if (allowInteractions) {
           selectionManager.select(d.selectionId); 
           ...
       }
   });
```