---
title: "SQL Server Database Components"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: faa5fd81-1ff7-4ce8-883a-1476ee6df0e1
caps.latest.revision: 19
manager: terryaus
---
# SQL Server Database Components
SQL Server database components configure Microsoft SQL Server to work with [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)].  
  
 If SQL Server is not present on the computer where you install the database components, then Setup automatically installs SQL Server Express 2014, which you can use for prototyping, developing, and testing. We recommend that you use SQL Server 2014 or SQL Server 2012 in production environments.  
  
 If you are installing the [!INCLUDE[demolong](../dynamics-nav/includes/demolong_md.md)], Setup will automatically install SQL Server Express 2014 if it does not find an existing NAVDEMO instance in SQL Server. So if you intend to install the [!INCLUDE[demo](../dynamics-nav/includes/demo_md.md)] database to an existing SQL Server installation, remember to create a NAVDEMO instance in SQL Server before you run [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Setup.  
  
 In [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Setup, SQL Server database components are a default component for the [Developer Option](../dynamics-nav/Developer-Option.md). You can add the components to the [Server Option](../dynamics-nav/Server-Option.md) or as part of a custom installation.  
  
 When you have installed the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] SQL Server database components on a database server, you can create new [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] databases in the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)][!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)], by using the [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)] commands, or by using the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Windows PowerShell cmdlets.  
  
## See Also  
 [Developer Option](../dynamics-nav/Developer-Option.md)   
 [Custom Option](../dynamics-nav/Custom-Option.md)   
 [Configuring Database Components](../dynamics-nav/Configuring-Database-Components.md)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](../dynamics-nav/Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)   
 [Development Environment Commands](../dynamics-nav/Development-Environment-Commands.md)