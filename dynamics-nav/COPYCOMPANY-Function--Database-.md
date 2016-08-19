---
title: "COPYCOMPANY Function (Database)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: dd8058d0-5b1e-4fd1-aeb1-7ef480fa581d
caps.latest.revision: 2
---
# COPYCOMPANY Function (Database)
Creates a new company and copies all data from an existing company in the same database.  
  
## Syntax  
  
```  
[Ok:=] COPYCOMPANY(SourceName, DestinationName)  
```  
  
#### Parameters  
 *SourceName*  
 Type: Text  
  
 The name of the company that you want to copy data from.  
  
 *DestinationName*  
 Type: Text  
  
 The name of the company that you want to create and copy data to.  
  
 The company name can have a maximum of 30 characters. If the database collation is case\-sensitive, you can have one company called COMPANY and another called Company. However, if the database is case\-insensitive, you cannot create companies with names that differ only by case.  
  
## Example  
 The following example is based on the **\($ B\_357 Copy Company $\)** batch job, which is part of the [!INCLUDE[demolong](includes/demolong_md.md)]. The batch job takes the [\($ T\_2000000006 Company $\)](../Topic/\($%20T_2000000006%20Company%20$\).md) system table as a data item and uses the **Name** field as the value of the *SourceName* parameter. The value of the *DestinationName* parameter is specified in the **New Company Name** field in the request page, which is represented by the `NewCompanyName` variable.  
  
```  
COPYCOMPANY(Name, NewCompanyName);  
```  
  
## See Also  
 [Database](Database.md)   
 [\($ B\_357 Copy Company $\)](../Topic/\($%20B_357%20Copy%20Company%20$\).md)