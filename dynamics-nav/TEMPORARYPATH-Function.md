---
title: "TEMPORARYPATH Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d770619b-4250-46d3-a602-5cef7334df6b
caps.latest.revision: 6
manager: pchapman
---
# TEMPORARYPATH Function
Gets the path of the directory where the temporary file for [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] is stored.  
  
## Syntax  
  
```  
  
TEMPORARYPATH  
```  
  
## Remarks  
 This function returns a string that contains the path of the directory where the temporary file for [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] is stored. This string ends with a backslash \('\\'\) and does not contain the name of the temp file.  
  
 The string cannot contain more than 255 characters.  
  
 If this function is called from an application that is running on a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Application Server, it returns the path of the directory where the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Application Server is installed.  
  
## See Also  
 [APPLICATIONPATH Function](../dynamics-nav/APPLICATIONPATH-Function.md)   
 [GUIALLOWED Function](../dynamics-nav/GUIALLOWED-Function.md)   
 [HYPERLINK Function](../dynamics-nav/HYPERLINK-Function.md)   
 [SLEEP Function](../dynamics-nav/SLEEP-Function.md)