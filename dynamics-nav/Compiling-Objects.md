---
title: "Compiling Objects"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 386dbfff-1518-4731-a2b1-424b556ed42a
caps.latest.revision: 14
manager: terryaus
---
# Compiling Objects
Before you can run a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] object, you must compile the object. To compile an object, do one of the following:  
  
-   In Object Designer, choose **Tools**, and then choose **Compile**. Any syntax errors are displayed in a dialog box. Any errors or warnings about obsolete constructs in a three\-tier environment are displayed in the **Error List** window.  
  
-   Run finsql.exe with the CompileObjects command. Any errors or warnings are added to the log file. For more information, see [CompileObjects](../dynamics-nav/CompileObjects.md).  
  
> [!NOTE]  
>  To compile an object, you must have a developer license.  
  
## Syntax Errors  
 Syntax errors are detected by the C\/AL compiler when you try to compile C\/AL code, either in a codeunit or as code in another object, such as a table, page, report, query, or XMLport. If you open an object in the designer and then compile the object, then if the compiler detects a syntax error, when you press ENTER and acknowledge the error message, the C\/AL editor opens with the cursor in front of the expression that has the error. If you compile an object directly from Object Designer and if the compiler detects a syntax error, then the C\/AL editor does not open to show where the error occurred.  
  
 The compiler will not compile code that contains a syntax error.  
  
## Obsolete Construct Errors  
 The following types of obsolete construct errors and warnings are displayed:  
  
-   Unsupported data type warnings for Binary and XMLport types.  
  
-   Unsupported function calls.  
  
> [!NOTE]  
>  Unsupported function calls for reports are not reported in the **Error List** window.  
  
 If you select an error in the **Error List** window and choose **Design**, then the C\/AL Editor opens for the object to which the error or warning relates.  
  
## Multilanguage Captions  
 When you compile application objects, [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] stores the objects in Unicode encoding. If the application objects contain multilanguage captions, [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] uses the code page that is relevant for the languages that you have specified. For more information, see [Developing Multilanguage\-Enabled Applications](../dynamics-nav/Developing-Multilanguage-Enabled-Applications.md).  
  
## See Also  
 [Compiling Tables](../dynamics-nav/Compiling-Tables.md)   
 [Objects](../dynamics-nav/Objects.md)   
 [Programming in C\-AL](../dynamics-nav/Programming-in-C-AL.md)