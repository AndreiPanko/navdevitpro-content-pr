---
title:"OnDrillDown Trigger"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: a25a1651-d138-497c-8dab-34bdf38ee17a
caps.latest.revision: 10
---
# OnDrillDown Trigger
Overrides the default drill\-down behavior defined in the table definition for the FlowField.  
  
## Applies To  
 Fields on pages  
  
> [!NOTE]  
>  The OnDrillDown trigger is not invoked on fields in a Repeater control in the [!INCLUDE[nav_web](includes/nav_web_md.md)].  
  
## Remarks  
 If there is an error in the trigger code, the drilldown is canceled. You can use this trigger to write to the database.  
  
 This trigger overrides the [DrillDownPageID Property](DrillDownPageID-Property.md) setting of the FlowField.  
  
## See Also  
 [Triggers](Triggers.md)