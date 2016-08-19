---
title: "Importing and Exporting Objects"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ee3d07c6-b153-4786-ac79-ffeaab477dcb
caps.latest.revision: 11
manager: terryaus
---
# Importing and Exporting Objects
You can import objects into [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] and export objects from [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] in the [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)] or by using development environment commands. The following table describes when you can use each method.  
  
|Method|Recommended uses|For more information|  
|------------|----------------------|--------------------------|  
|**Import** and **Export** from the **File** menu in the [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)].|To move, copy, or share objects from Object Designer.|[How to: Import Objects](../Topic/How%20to:%20Import%20Objects.md)<br /><br /> [How to: Export Objects](../Topic/How%20to:%20Export%20Objects.md)<br /><br /> [Import Worksheet](../dynamics-nav/Import-Worksheet.md)|  
|ImportObjects and ExportObjects commands.|To move, copy, or share objects at a command prompt. Use the commands if you want to automate the import or export.|[Development Environment Commands](../dynamics-nav/Development-Environment-Commands.md)<br /><br /> [How to: Import Objects](../Topic/How%20to:%20Import%20Objects.md)<br /><br /> [How to: Export Objects](../Topic/How%20to:%20Export%20Objects.md)|  
  
 When you export an object, you export the design object, but not the data, from the database.  
  
> [!WARNING]  
>  When you import objects to [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] from a .txt file, and the file contains syntax errors, the objects are not imported. You must correct the error and import the .txt file again.  
  
 To translate strings for customized objects in a multilanguage environment, you can import and export text strings. For more information, see [How to: Add Translated Strings By Importing and Exporting Multilanguage Files](../Topic/How%20to:%20Add%20Translated%20Strings%20By%20Importing%20and%20Exporting%20Multilanguage%20Files.md). Alternatively, you can export your application objects into text files and then use [!INCLUDE[wps_2](../dynamics-nav/includes/wps_2_md.md)] cmdlets to export and import languages. For more information, see [Working with Application Objects as Text Files](../dynamics-nav/Working-with-Application-Objects-as-Text-Files.md).  
  
 To view or troubleshoot a report on a computer that does not have [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] installed, you can export the dataset of a report as an .xml file. This exports the structure of the dataset and the data from the report. For more information, see [Walkthrough: Running a Report Offline](../Topic/Walkthrough:%20Running%20a%20Report%20Offline.md).  
  
## See Also  
 [How to: Import Objects](../Topic/How%20to:%20Import%20Objects.md)   
 [How to: Export Objects](../Topic/How%20to:%20Export%20Objects.md)   
 [ImportObjects](../dynamics-nav/ImportObjects.md)   
 [Objects](../dynamics-nav/Objects.md)   
 [How to: Add Translated Strings By Importing and Exporting Multilanguage Files](../Topic/How%20to:%20Add%20Translated%20Strings%20By%20Importing%20and%20Exporting%20Multilanguage%20Files.md)   
 [Import Worksheet](../dynamics-nav/Import-Worksheet.md)   
 [Working with Application Objects as Text Files](../dynamics-nav/Working-with-Application-Objects-as-Text-Files.md)