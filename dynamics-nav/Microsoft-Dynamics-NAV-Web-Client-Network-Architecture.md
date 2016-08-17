---
title: "Microsoft Dynamics NAV Web Client Network Architecture"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d38680b1-7341-4170-b7ef-389ac005c8a5
caps.latest.revision: 8
manager: terryaus
---
# Microsoft Dynamics NAV Web Client Network Architecture
The following illustration shows the four tiers of the network architecture in the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)].  
  
 ![NAV Web Client network architecture](../dynamics-nav/media/NAV_WebClient_Network_Architecture.png "NAV\_WebClient\_Network\_Architecture")  
  
 The following table describes the components of each tier.  
  
|Tier|Description|  
|----------|-----------------|  
|Device|A computer or device that has access to the Internet with a browser. For a list of supported browsers, see [System Requirements for Microsoft Dynamics NAV 2016](../dynamics-nav/System-Requirements-for-Microsoft-Dynamics-NAV-2016.md).|  
|Web server|A computer that is running Internet Information Services \(IIS\) at a minimum. [!INCLUDE[nav_web_server](../dynamics-nav/includes/nav_web_server_md.md)] are installed on a website on IIS. For more information, see [How to: Install the Web Server Components](../Topic/How%20to:%20Install%20the%20Web%20Server%20Components.md).|  
|[!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)]|A Microsoft .NET Framework–based Windows Service that manages communications and provides a security layer between clients and [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] databases in SQL Server. For more information, see [Microsoft Dynamics NAV Server](../dynamics-nav/Microsoft-Dynamics-NAV-Server.md).|  
|Database|A SQL Server database that contains [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] data. For more information, see [SQL Server Database Components](../dynamics-nav/SQL-Server-Database-Components.md).|