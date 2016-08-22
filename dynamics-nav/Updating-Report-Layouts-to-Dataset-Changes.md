---
title: "Updating Report Layouts to Dataset Changes"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: c0d73d5e-61dc-4a86-9976-56e7a3056f34
caps.latest.revision: 10
---
# Updating Report Layouts to Dataset Changes
When you make changes to the report dataset, the report layouts that are used on the report must to be updated to the changes. The process for updating report layouts is different for built\-in layouts and custom layouts.  
  
## Updating Built\-in Report Layouts  
 With most changes to a report dataset, such as adding or renaming a field, the built\-in report layout will automatically be updated to the changes when you compile the report. However, there are certain dataset changes, such as deleting a field or changing a field's ID, which cannot be updated in the built\-in report layout automatically. With these types of changes, you will get an error, which includes a description of the problem, when you try to compile the report. To update a built\-in report layout to dataset changes in these cases, you must manually modify the report layout in Word, Visual Studio, or SQL Report Builder, depending on the report layout type, and fix any errors that are caused by the changes. After you modify the built\-in layout, you can compile the report.  
  
 For more information, see [How to: Modify a Word Report Layout](../Topic/How%20to:%20Modify%20a%20Word%20Report%20Layout.md) or [Designing RDLC Report Layouts](Designing-RDLC-Report-Layouts.md).  
  
## Updating Custom Report Layouts  
 The process for updating custom report layouts is different than for built\-in report layouts because custom report layouts are stored in the [!INCLUDE[navnow](includes/navnow_md.md)] database for a company and are not part of the report object like built\-in report layouts. There are two ways to update custom report layouts. You can use the report layout update feature from the [!INCLUDE[navnow](includes/navnow_md.md)] client or you can programmatically update the custom reports layouts by upgrade codeunits.  
  
-   Updating custom report layouts from the [!INCLUDE[navnow](includes/navnow_md.md)] client  
  
     The report layout update feature in the [!INCLUDE[navnow](includes/navnow_md.md)] client enables end\-users to update the custom reports layouts. The report update feature can handle many types of changes to a report dataset, such as adding or renaming a field \(column\). However, similar to built\-in report layouts, there are some changes that cannot be handled by the report update feature. To fix these changes from the client, the user will have to open and modify the report layout manually.  
  
     For more information about updating custom report layouts from the [!INCLUDE[navnow](includes/navnow_md.md)] client, see [Updating Report Layouts](../Topic/Updating%20Report%20Layouts.md) in the Application Help for [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  
  
-   Programmatically updating custom report layouts using upgrade codeunits  
  
     Using C\/AL code and the report update API enables you to accomplish two things. You can handle report dataset changes that cannot be done by the report update feature from the client, such as deleted columns in the dataset. It also enables you to update custom report layouts with minimal end\-user interaction.  
  
     For more information, see [Updating Report Layouts to Dataset Changes](Updating-Report-Layouts-to-Dataset-Changes.md).  
  
## See Also  
 [Built-in and Custom Report Layouts](../Topic/About%20Report%20Layouts.md#BuiltinLayout)   
 [Designing RDLC Report Layouts](Designing-RDLC-Report-Layouts.md)   
 [Designing Word Report Layouts](Designing-Word-Report-Layouts.md)