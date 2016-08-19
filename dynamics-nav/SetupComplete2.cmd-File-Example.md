---
title: "SetupComplete2.cmd File Example"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a6484034-a4cc-4d11-9222-7ea6727c8770
caps.latest.revision: 7
manager: tsiggaar
---
# SetupComplete2.cmd File Example
The following code is an example of the SetComplete2.cmd file on a Microsoft Azure virtual machine. When you create an Azure virtual machine that you want to use as an Azure Marketplace image for [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] deployment, you use the SetComplete2.cmd file to Schedule the second part of SysPrep\-based SQL Server installation on the Azure virtual machine that is created from the image.  
  
 Copy the following code into the SetComplete2.cmd file.  
  
```  
@ECHO OFF && SETLOCAL && SETLOCAL ENABLEDELAYEDEXPANSION && SETLOCAL ENABLEEXTENSIONS  
REM All commands will be executed during first Virtual Machine boot  
  
"C:\Program Files\Microsoft SQL Server\110\Setup Bootstrap\SQLServer2012\setup.exe" /QS /ACTION=CompleteImage /INSTANCEID=MSSQLSERVER /INSTANCENAME=MSSQLSERVER /IACCEPTSQLSERVERLICENSETERMS=1 /SQLSYSADMINACCOUNTS=%COMPUTERNAME%\Administrator /BROWSERSVCSTARTUPTYPE=AUTOMATIC /INDICATEPROGRESS /TCPENABLED=1  
  
```  
  
 For more information about how to use the SetComplete2.cmd file, see [How to: Create a Microsoft Azure Virtual Machine Operating System Image for Microsoft Dynamics NAV](../Topic/How%20to:%20Create%20a%20Microsoft%20Azure%20Virtual%20Machine%20Operating%20System%20Image%20for%20Microsoft%20Dynamics%20NAV.md).  
  
## See Also  
 [How to: Create a Microsoft Azure Virtual Machine Operating System Image for Microsoft Dynamics NAV](../Topic/How%20to:%20Create%20a%20Microsoft%20Azure%20Virtual%20Machine%20Operating%20System%20Image%20for%20Microsoft%20Dynamics%20NAV.md)   
 [SQL Server Sysprep Installation Configuration File Example](../dynamics-nav/SQL-Server-Sysprep-Installation-Configuration-File-Example.md)   
 [Preparing for Deploying Microsoft Dynamics NAV on Microsoft Azure](../dynamics-nav/Preparing-for-Deploying-Microsoft-Dynamics-NAV-on-Microsoft-Azure.md)   
 [Preparing a Microsoft Azure Virtual Machine Image for Microsoft Dynamics NAV](../dynamics-nav/Preparing-a-Microsoft-Azure-Virtual-Machine-Image-for-Microsoft-Dynamics-NAV.md)