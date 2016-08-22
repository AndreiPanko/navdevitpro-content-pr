---
title: "How to: Add Users for ADCS"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 4c5564b0-f01d-47af-b2f6-9f7587afd449
caps.latest.revision: 9
manager: edupont
translation.priority.ht: 
  - da-dk
  - de-at
  - de-ch
  - de-de
  - en-au
  - en-ca
  - en-gb
  - en-in
  - en-nz
  - es-es
  - es-mx
  - fi-fi
  - fr-be
  - fr-ca
  - fr-ch
  - fr-fr
  - is-is
  - it-ch
  - it-it
  - nb-no
  - nl-be
  - nl-nl
  - ru-ru
  - sv-se
---
# How to: Add Users for ADCS
You can add any user as a user of an Automated Data Capture System \(ADCS\). When you do this, the user must also provide a password. Optionally, you can also provide a connection that identifies the ADCS user as a warehouse employee. The ADCS user password can be different from the Windows logon password of the user.  
  
### To add an ADCS user  
  
1.  In the **Search** box, enter **\($ N\_7710 ADCS Users $\)**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New** to add a new user.  
  
3.  In the **\($ T\_7710\_1 Name $\)** field, enter a name for the user. The name cannot contain more than 20 characters, including spaces.  
  
4.  In the **\($ T\_7710\_2 Password $\)** field, enter a password. The password is masked.  
  
### To indicate that a warehouse employee is an ADCS user  
  
1.  In the **Search** box, enter **\($ N\_7328 Warehouse Employees $\)**, and then choose the related link.  
  
2.  If needed, add a new warehouse employee. For more information, see [How to: Set Up Warehouse Employees](../Topic/How%20to:%20Set%20Up%20Warehouse%20Employees.md).  
  
3.  On the **Home** tab, in the **Manage** group, choose **Edit List**.  
  
4.  Select a warehouse employee from the list. In the **\($ T\_7301\_7710 ADCS User $\)** field, choose the drop\-down arrow, and then select the name of an ADCS user from the list.  
  
    > [!NOTE]  
    >  The default warehouse for the employee should be one that uses ADCS. For more information, see [How to: Set Up a Warehouse to Use ADCS](../Topic/How%20to:%20Set%20Up%20a%20Warehouse%20to%20Use%20ADCS.md).  
  
## See Also  
 [\($ N\_7710 ADCS Users $\)](../Topic/\($%20N_7710%20ADCS%20Users%20$\).md)   
 [\($ T\_7301\_7710 ADCS User $\)](../Topic/\($%20T_7301_7710%20ADCS%20User%20$\).md)   
 [How to: Test the ADCS Connection](../Topic/How%20to:%20Test%20the%20ADCS%20Connection.md)   
 [How to: Create Microsoft Dynamics NAV Users](../Topic/How%20to:%20Create%20Microsoft%20Dynamics%20NAV%20Users.md)