---
title: "Installation Considerations for Microsoft SQL Server and Microsoft Dynamics NAV"
ms.custom: na
ms.date: 09/14/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 0c1e0c2f-e8c1-412e-86a8-6a2ba944af24
caps.latest.revision: 31
manager: edupont
---
# Installation Considerations for Microsoft SQL Server and Microsoft Dynamics NAV
This topic describes the requirements for installing and configuring Microsoft SQL Server to work with [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  

[!INCLUDE[navnow_md](includes/navnow_md.md)] can run on Microsoft SQL Server and Microsoft Azure SQL Database. For a list of supported editions of SQL Server, see [Microsoft Dynamics NAV Database Components for SQL Server Requirements](System-Requirements-for-Microsoft-Dynamics-NAV.md#SQLReq).  

## Using Microsoft SQL Server

### Storage
Use different disks or disk partitions for the following:
-   Windows operating system.
-   Data files for the system databases.
-   Log files for system and user databases.
-   Data and log files for the TempDB database.

For optimal read/write performance, make sure that disks that are used for SQL Server data files are formatted using 64 KB block size.

### Virus scanning
To help you decide which kind of antivirus software to use on the computers that are running Microsoft SQL Server in your environment, see [How to choose antivirus software to run on computers that are running SQL Server](https://aka.ms/chooseantivirussoftwareforsqlserver).

### Memory
For optimal read performance, maximize the available memory on the server according to the version and edition of SQL Server used. Refer to the SQL Server documentation for maximum values.

### SQL Server Components  
If you are installing Microsoft SQL Server for use with [!INCLUDE[navnow](includes/navnow_md.md)], then install the following components:  
-   Database Engine Services  
-   Client Tools Connectivity  
-   Management Tools - Complete  

### Setup Options for Microsoft SQL Server  
When you are running Microsoft SQL Server Setup, you must provide additional information. Your responses can affect how you use SQL Server with [!INCLUDE[navnow_md](includes/navnow_md.md)].  

#### TempDB database configuration
For servers with less than 8 cores, create as many datafiles for the TempDB database as the number of cores. For servers with more than 8 cores, start with 8 datafiles, and increment with 4 files at a time, if needed.

Make sure that all datafiles for the TempDB database are of the same size.

Consider putting data and log files for TempDB on a local SSD drive if you are using SAN storage.

#### Instance Configuration  
 If you plan on installing the [!INCLUDE[navnow](includes/navnow_md.md)] Demo database, and you want [!INCLUDE[navnow](includes/navnow_md.md)] Setup to use an already installed version of SQL Server \(and not to install SQL Server Express\), you must create a SQL Server instance named **NAVDEMO** in SQL Server before you run Setup. Otherwise, Setup will install SQL Server Express automatically, even if there is a valid version of SQL Server already on the computer. If you do not plan to install the Demo database, or if you have no objection to using SQL Server Express, you are free to use the **default instance** and **Instance ID** on the **Instance Configuration** page, or to specify any instance name.  

### Database Engine Service Startup Options
Enable trace flags 1117 and 1118 as startup options for SQL Server versions 2012 and 2014 (they are enabled by default in SQL Server 2016.)

Startup options can be set by using SQL Server Configuration Manager, see the SQL Server documentation for details.

### SQL Server engine service account
 We recommend that you use a dedicated domain user account that you create specifically for your [!INCLUDE[nav_server](includes/nav_server_md.md)] instances and for your [!INCLUDE[navnow](includes/navnow_md.md)] instance on SQL Server, instead of a Local System account or the Network Service account.  

For installations on SQL Server 2012 and 2014, consider adding the SQL Server engine service account to the **Perform Volume Maintenance Tasks** security policy.

## Using Microsoft Azure SQL Database  
 You can deploy a [!INCLUDE[navnow](includes/navnow_md.md)] database to Azure SQL Database. Azure SQL Database is a cloud service that provides data storage as a part of the Azure Services Platform.  

 To optimize performance, we recommend that the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that connects to the database is also deployed on a virtual machine in Azure. Additionally, the virtual machine and SQL Database must be in the same Azure region.  

 For development and maintenance work on [!INCLUDE[navnow](includes/navnow_md.md)] applications, if the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] is installed on the same virtual machine in Azure as the [!INCLUDE[nav_server](includes/nav_server_md.md)], then you can connect to the Azure SQL database from the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)].  

 For more information, see [How to: Deploy a Microsoft Dynamics NAV Database to Azure SQL Database](How-to--Deploy-a-Microsoft-Dynamics-NAV-Database-to-Azure-SQL-Database.md).  

## Data Encryption Between [!INCLUDE[nav_server](includes/nav_server_md.md)] and SQL Server  
 When SQL Server and [!INCLUDE[nav_server](includes/nav_server_md.md)] are running on different computers, you can make this data channel more secure by encrypting the connection with IPSec. \(Other encryption options are not supported.\) For information on how to do this, see [Encrypting Connections to SQL Server](http://go.microsoft.com/fwlink/?LinkId=147732), which is part of SQL Server 2008 Books Online in MSDN library.  

## See Also  
 [Data Access](Data-Access.md)   
 [Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
 [Troubleshooting: SQL Server Connection Problems](Troubleshooting--SQL-Server-Connection-Problems.md)   
 [Deployment](Deployment.md)
