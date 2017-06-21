---
title: "Programming in AL"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
ms.assetid: 5ee737ae-3914-47e7-b61d-486309b7fa8f
caps.latest.revision: 19
author: jswymer
---
# Programming in AL
This section describes where to write AL code and how to reuse code.  

 For more information about how to use system-defined variables, see [System-Defined Variables](devenv-system-defined-variables.md).  

 For more information about the most frequently used AL methods, see [Essential AL Methods](devenv-essential-al-methods.md).  

## Where to Write AL Code  
 Almost every object in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] contains triggers where you can add your AL code. Triggers exist for the following objects:  

-   Tables  

-   Table fields  

-   Pages, including request pages  

-   Reports  

-   Data items  

-   XMLports  

-   Queries  

 You can initiate the execution of your AL code from the following:  

-   Actions  

-   Menu items  

-   Any object that has an instantiation of the object that contains AL code. An example of an instantiation is a variable declaration.  

    > [!NOTE]  
    >  If the AL code is in a local function, then you cannot run it from another object.  


## Guidelines for Placing AL Code  
 We recommend the following guidelines for AL code:  

-   In general, put the code in codeunits instead of on the object on which it operates. This promotes a clean design and provides the ability to reuse code. It also helps enforce security. For example, typically users do not have direct access to tables that contain sensitive data, such as the **General Ledger Entry** table, nor do they have permission to modify objects. If you put the code that operates on the general ledger in a codeunit, give the codeunit access to the table, and give the user permission to execute the codeunit, then you will not compromise the security of the table and the user will be able to access the table.  

-   If you must put code on an object instead of in a codeunit, then put the code as close as possible to the object on which it operates. For example, put code that modifies records in the triggers of the table fields.  

## Reusing Code  
 Reusing code makes developing applications both faster and easier. More importantly, if you organize your AL code as suggested, your applications will be less prone to errors. By centralizing the code, you will not unintentionally create inconsistencies by performing the same calculation in many places, for example, in several triggers that have the same table field as their source expression. If you have to change the code, you could either forget about some of these triggers or make a mistake when you modify one of them.  

## See Also  
 [System-Defined Variables](devenv-system-defined-variables.md)   
 [Essential AL Methods](devenv-essential-al-methods.md)
