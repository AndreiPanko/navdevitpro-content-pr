---
title: Converting to Shared Schema
description: Explains the shared schema data model and how to convert to it from the default separate schema data model.
ms.date: 10/16/2017
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
author: jswymer
---
# Converting a Tenant From Shared Schema to Separate Schema
This article explains how you can convert a tenant that uses the shared schema data model to use the separate schema data model. 

1. Using the [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], create an empty [!INCLUDE[navnow_md](includes/navnow_md.md)] database.

    For more information, see [How to: Create Databases](How-to--Create-Databases.md).

2. Use the [Mount-NAVTenantDatabase cmdlet](https://go.microsoft.com/fwlink/?linkid=838753) of the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)] to mount the new database to the same [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance as the tenant that you want to move.

    ```
     Mount-NAVTenantDatabase -ServerInstance '[nav_server_instance_name]' -Id '[tenant_database_ID]' -DatabaseName '[new_database_name]' -DatabaseServer '[database_server_name]\[database_instance_name]'
    ```
    Subsitute `[tenant_database_ID]`with the ID that you want to assign the database. You will use this ID in the steps that follow. Substitute the remaining brackets `[ ]` to suit. 

3. Use the Sync-NAVTenantDatabase cmdlet to synchronize the schema of the new database with the application database schema.

    ```
     Sync-NAVTenantDatabase -ServerInstance '[nav_server_instance_name]' -Id '[tenant_database_ID]'
    ```
    This changes the state of the new database from **PendingSync** to **Operational**.

4. Use the Move-NAVtenant cmdlet to move the tenant to the new database.

    ```
    Move-NAVTenant -ServerInstance '[nav_server_instance_name]' -Tenant [tenant_ID] -DestinationTenantDatabaseId [tenant_database_ID]'
    ```

    When the move operation finishes, the tenant's data has been moved to the new database.

5. (Optional) In the original database, a record of the tenant is still mounted on the server instance. The tenant's state is **Deleted** so it cannot be accessed. The tenant ID has been suffixed with a GUID, such as `tenantIDfafc27d4e46540e5b64c0c060db5abbc`. To delete the tenant record from the original database, you have to dismount the tenant.

    1.  Use the Get-NAVTenant cmdlet to get the modified tenant ID in the original database:

        ```
        Get-NAVTenant -ServerInstance '[nav_server_instance_name]' 
        ```
    
    2.  Use the Dismount-NAVTenant cmdlet to dismount the tenant from the server instance.

        ```
        Dismount-NAVTenant -ServerInstance '[nav_server_instance_name]' -Tenant '[modified_tenant_ID]'
        ```

## See Also  
[Converting a Database to Shared Schema](convert-database-to-shared-schema.md)
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)   
[Migrating to Multitenancy](Migrating-to-Multitenancy.md)  
[Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
[Configuring Microsoft Dynamics NAV](Configuring-Microsoft-Dynamics-NAV.md)  
