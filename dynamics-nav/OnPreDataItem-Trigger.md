---
title: "OnPreDataItem Trigger"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 4b6df5e3-5346-4171-8113-54e098e4bc02
caps.latest.revision: 7
---
# OnPreDataItem Trigger
Executed before a data item is processed.  
  
## Applies To  
 Data items  
  
## Remarks  
 This trigger is executed before a data item is processed, but after the associated variable is initialized and table views and filters are set.  
  
 You can use this trigger to add additional filtering beyond what is established by the [DataItemLink Property \(Reports\)](../dynamics-nav/DataItemLink-Property--Reports-.md) or [DataItemTableView Property](../dynamics-nav/DataItemTableView-Property.md). For example, use this trigger if you need to filter an indented data item based on the result of a calculation. Use the [SETRANGE Function \(Record\)](../dynamics-nav/SETRANGE-Function--Record-.md) or [SETFILTER Function \(Record\)](../dynamics-nav/SETFILTER-Function--Record-.md) function to add extra delimiters.  
  
## See Also  
 [DataItemLink Property \(Reports\)](../dynamics-nav/DataItemLink-Property--Reports-.md)   
 [DataItemTableView Property](../dynamics-nav/DataItemTableView-Property.md)   
 [SETRANGE Function \(Record\)](../dynamics-nav/SETRANGE-Function--Record-.md)   
 [SETFILTER Function \(Record\)](../dynamics-nav/SETFILTER-Function--Record-.md)