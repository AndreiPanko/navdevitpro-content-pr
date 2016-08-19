---
title: "XMLports"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: aa8d94aa-1cea-4602-8f8f-9fd49ffb54f1
caps.latest.revision: 26
manager: terryaus
---
# XMLports
XMLports are used to export or import data between an external source and a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] database. Sharing data between different computer systems is seamless when it is shared in XML format. Working with XML files can be tedious so the details of how the XML file is handled are encapsulated in XMLports.  
  
 To use an XMLport to import or export data, you first design the XMLport in the XMLport Designer window and set some properties. You can run the XMLport from Object Designer or create a codeunit to run the XMLport. For more information about how to run XMLports in a codeunit, see [How to: Create Codeunits to Run XMLports](../Topic/How%20to:%20Create%20Codeunits%20to%20Run%20XMLports.md). For information about how to run XMLports in Object Designer, see [How to: Run an XMLport from Object Designer](../Topic/How%20to:%20Run%20an%20XMLport%20from%20Object%20Designer.md).  
  
 If you are upgrading from an earlier version of [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] and used Dataports in the earlier version, then you should analyze the functionality of each Dataport and re\-create that functionality in [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] using XMLports.  
  
## Introducing XMLports  
 The following table lists topics that provide detailed information about how to use XMLports.  
  
|To|See|  
|--------|---------|  
|Read about the XMLport Designer window.|[\($ S\_21001 XMLport Designer $\)](../dynamics-nav/-$-S_21001-XMLport-Designer-$-.md)|  
|Read about triggers available for XMLports and XMLport elements.|[XMLport Triggers](../dynamics-nav/XMLport-Triggers.md)|  
|Learn how to design an XMLport for import or export.|-   [Designing XMLports](../dynamics-nav/Designing-XMLports.md)<br />-   [How to: Create XMLports](../Topic/How%20to:%20Create%20XMLports.md)|  
|Learn how to create codeunits to run XMLports.|[How to: Create Codeunits to Run XMLports](../Topic/How%20to:%20Create%20Codeunits%20to%20Run%20XMLports.md)|  
|Learn about designing request pages for XMLports|[Request Pages \(XMLPorts\)](../dynamics-nav/Request-Pages--XMLPorts-.md)|  
|Learn how to run XMLports from Object Designer.|[How to: Run an XMLport from Object Designer](../Topic/How%20to:%20Run%20an%20XMLport%20from%20Object%20Designer.md)|  
|Read about XMLport data types and functions.|[XMLport Data Type](../dynamics-nav/XMLport-Data-Type.md)|  
  
## XMLports Walkthroughs  
 The following table lists topics that provide information about how to use XMLports to create scenario based applications.  
  
|To|See|  
|--------|---------|  
|Learn how to export data from a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] table into an XML document.|[Walkthrough: Exporting Data from Tables to XML Documents](../Topic/Walkthrough:%20Exporting%20Data%20from%20Tables%20to%20XML%20Documents.md)|  
|Learn how to import data from an XML document to multiple tables in a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] database. The XML document contains data that belongs in two different tables in the database.|[Walkthrough: Inserting Data from XML Documents to Multiple Tables](../Topic/Walkthrough:%20Inserting%20Data%20from%20XML%20Documents%20to%20Multiple%20Tables.md)|  
|Learn how to export data from tables to CSV \(comma separated value\) files.|[Walkthrough: Exporting Data from Tables to CSV Files](../Topic/Walkthrough:%20Exporting%20Data%20from%20Tables%20to%20CSV%20Files.md)|  
|Learn how to import data from text files.|[Walkthrough: Importing Data from Text Files to Tables](../Topic/Walkthrough:%20Importing%20Data%20from%20Text%20Files%20to%20Tables.md)|  
  
## See Also  
 [Designing XMLports](../dynamics-nav/Designing-XMLports.md)