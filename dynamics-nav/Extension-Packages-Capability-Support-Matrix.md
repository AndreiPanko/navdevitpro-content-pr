---
title: "Extension Packages Capability Support Matrix"
author: edupont04
ms.custom: na
ms.date: 11/02/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 83351319-ce8a-4a84-9831-f68ed9f14835
ms.author: edupont
---
# Extension Packages Capability Support Matrix
An extension package can contain both new and modified objects. In [!INCLUDE[navnowlong](includes/navnowlong_md.md)], the following object types can be added and included in an extension:  

- Pages
- Tables
- Reports
- XMLports
- Queries
- Codeunits
- Menu suites  

 You cannot add or modify any other object types in this version. Also, you cannot delete any existing objects.  

> [!IMPORTANT]  
>  You cannot modify any existing C/AL code, including code in codeunits and in triggers on existing objects. If you want to modify existing code, use the new C/AL eventing model. This restriction is only on existing code and objects. New pages, tables, and so on, can contain C/AL code as it is considered part of the new object.  

In addition to the object types described above, you are also able to include .NET Interop server add-ins, client-side JavaScript, WinForms extensibility control add-ins, starting data, permission sets, per-tenant web services, and multilanguage files.

## Restricted properties  
 There are restrictions on certain property changes for modified objects. The following sections list the properties you cannot change. The cmdlets that create and install packages will halt with errors if any of these properties are changed in your extension.  

### Restricted properties on existing page modifications  
 You cannot change the values for the following properties for existing [!INCLUDE[navnow](includes/navnow_md.md)] pages in an extension.  

-   AccessByPermission  

-   AssistEdit  

-   AutoSplitKey  

-   CardPageID  

-   CharAllowed  

-   ContainerType  

-   ControlAddIn  

-   Data Type  

-   DataLength  

-   DateFormula  

-   DelayedInsert  

-   DeleteAllowed  

-   DrillDown  

-   DrillDownPageID  

-   Editable  

-   ExtendedDatatype  

-   FieldClass  

-   GroupType  

-   ID  

-   InsertAllowed  

-   LinkedObject  

-   Lookup  

-   LookupPageID  

-   MaxValue  

-   MinValue  

-   ModifyAllowed  

-   MultipleNewLines  

-   Name  

-   NotBlank  

-   Numeric  

-   PageType  

-   PartType  

-   PasteIsValid  

-   Permissions  

-   PopulateAllFields  

-   RefreshOnActivate  

-   SourceExpr  

-   SourceTable  

-   SourceTableTemporary  

-   SourceTableView  

-   SubType  

-   SystemPartID  

-   TableRelation  

-   TableType  

-   TestTableRelation  

-   ValidateTableRelation  

-   ValuesAllowed  

 Most of these are typically not properties changed through customization as they can have a negative effect on the [!INCLUDE[navnow](includes/navnow_md.md)] deployment.  

### Restricted properties on existing table modifications  
 You cannot change the values for the following properties for existing tables and fields in an extension.  

|Table Properties|Field Properties|  
|----------------------|----------------------|  
|-   Name<br />-   DataPerCompany<br />-   Permissions<br />-   LookupPageID<br />-   DrillDownPageID<br />-   PasteIsValid<br />-   LinkedObject<br />-   TableType|-   Name<br />-   AccessByPermission<br />-   Compressed<br />-   Data Type<br />-   DataLength<br />-   DateFormula<br />-   ExtendedDataType<br />-   FieldClass<br />-   MaxValue<br />-   MinValue<br />-   NotBlank<br />-   Numeric<br />-   Owner<br />-   SQL Data Type<br />-   SubType \(BLOB\)<br />-   TableIDExpr<br />-   TableRelation<br />-   TestTableRelation<br />-   ValidateTableRelation<br />-   ValuesAllowed Width|  

 You can add table keys, but you cannot delete or modify existing keys.  

 You can add fields to a table group, but you cannot remove fields or groups.  

## See Also  
 [Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md)   
 [Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)
