---
title: "Cryptography Overview"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 7e0817eb-59cd-411c-ab81-bf3d8e17844d
caps.latest.revision: 4
manager: edupont
---
# Cryptography Overview
The functions that support cryptography in [!INCLUDE[navnow](includes/navnow_md.md)] provide services that enable developers to add security for encrypting and decrypting data and key management. Each [!INCLUDE[navnow](includes/navnow_md.md)] tenant supports a single encryption key which is used for encrypting and decrypting data stored in the database. Additional functions are provided to assist building robust solutions when working with encryption and for managing the encryption keys.  
  
 ![Flow between plain text and encrypted text](media/NAV_Encryption.jpg "NAV\_Encryption")  
  
## Encryption Keys  
 To encrypt and decrypt text, we use an encryption key. [!INCLUDE[navnow](includes/navnow_md.md)] stores the key in a secure location and accesses it at runtime when needed. Additional functionality is provided to export and import keys, which is important when moving solutions from one location to another. For more information, see [Encryption Key Management](Encryption-Key-Management.md) and [Encryption Functions](Encryption-Functions.md).  
  
## See Also  
 [Encryption Key Management](Encryption-Key-Management.md)   
 [Programming in C-AL](Programming-in-C-AL.md)   
 [How to: Export and Import Encryption Keys](How-to--Export%20and%20Import%20Encryption%20Keys.md)   
 [How to: Enable and Disable Encryption Keys](How-to--Enable%20and%20Disable%20Encryption%20Keys.md)   
 [Manage Data Encryption](Manage%20Data%20Encryption.md)