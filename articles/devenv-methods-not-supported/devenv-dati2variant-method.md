---
title: "DATI2VARIANT Method"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: f07bd168-5e97-475d-aced-be6c0e942c90
caps.latest.revision: 9
manager: edupont
---
# DATI2VARIANT Method
Creates a variant that contains an encapsulation of a COM VT\_DATE.  
  
## Syntax  
  
```  
  
Variant := DATI2VARIANT(Date, Time)  
```  
  
#### Parameters  
 *Date*  
 Type: Date  
  
 The input date.  
  
 *Time*  
 Type: Time  
  
 The input time.  
  
## Property Value/Return Value  
 Type: Variant  
  
## Example  
 This example requires that you create the following variables.  
  
|Name|DataType|  
|----------|--------------|  
|TestDate|Date|  
|TestTime|Time|  
|Variant1|Variant|  
  
```  
TestDate := TODAY;  
TestTime := TIME;  
Variant1 := DATI2VARIANT(TestDate, TestTime);  
```  
  
## See Also  
 [Variant Data Type](Variant-Data-Type.md)   
 [Date and Time Methods](Date-and-Time-Methods.md)   
 [Using COM Technologies in Microsoft Dynamics NAV](Using-COM-Technologies-in-Microsoft-Dynamics-NAV.md)