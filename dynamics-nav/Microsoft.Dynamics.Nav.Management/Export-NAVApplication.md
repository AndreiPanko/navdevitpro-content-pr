---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401355
schema: 2.0.0
---

# Export-NAVApplication

## SYNOPSIS
Extracts the application tables in a Microsoft Dynamics NAV database to a separate database.
The new application database is created on the same SQL Server instance as the original database.

## SYNTAX

```
Export-NAVApplication [-DatabaseServer <DatabaseServer>] [-DatabaseInstance <DatabaseInstance>]
 -DatabaseName <DatabaseName> -DestinationDatabaseName <DatabaseName> [-ServiceAccount <String>] [-Force]
 [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Export-NavApplication cmdlet to export the tables that define the Microsoft Dynamics NAV application to a dedicated database.
If you want to deploy your Microsoft Dynamics NAV solution in a multitenant deployment architecture, you must separate the application tables in an existing database into two databases: an application database and a business data database.
You can combine the Export-NavApplication cmdlet with the Remove-NAVApplication cmdlet.
Before you use the Export-NavApplication cmdlet, we recommend that you create a full backup of your existing database.

## EXAMPLES

### EXAMPLE 1
```
Export-Application -DatabaseName 'Demo Database NAV' -DestinationDatabaseName NAVApp
```

This example extracts the application tables from the specified database to a new application database on the local server.

### EXAMPLE 2
```
Export-Application -DatabaseName 'Demo Database NAV' -DestinationDatabaseName NAVApp -ServiceAccount 'mydomain\navdbaccount'
```

This example extracts the application tables from the specified database to a new application database on the local server.

### EXAMPLE 3
```
Export-NAVApplication -DatabaseServer 'MyServer' -DatabaseInstance 'NavDemo' -DatabaseName 'Demo Database NAV' -DestinationDatabaseName 'NAV App'
```

This example extracts the application tables from the specified database to a new application database on the specified server and instance.

### EXAMPLE 4
```
Export-NAVApplication -DatabaseServer 'MyServer' -DatabaseInstance 'NavDemo' -DatabaseName 'Demo Database NAV' -DestinationDatabaseName 'NAV App' | Remove-NAVApplication -Force
```

This example extracts the application tables from the specified database to a new application database on the specified server and instance.
It then pipes the name of the database to the Remove-NAVApplication cmdlet, which removes the application tables from the original database.

## PARAMETERS

### -DatabaseInstance
Specifies the SQL Server instance on which the Microsoft Dynamics NAV database is installed.
The new application database will be created on the same SQL Server instance as the original database.

```yaml
Type: DatabaseInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the Microsoft Dynamics NAV database that contains the application tables, such as 'Demo Database NAV (8-0)'.
This database is the original database that application tables will be extracted from.

```yaml
Type: DatabaseName
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the name of the computer on which the SQL Server instance for the Microsoft Dynamics NAV database is installed.

```yaml
Type: DatabaseServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationDatabaseName
Specifies the name of the database that you want to export the tables to.
If a database with that name does not exist, a new database is created on the same SQL Server instance as the original database.

```yaml
Type: DatabaseName
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccount
The account that Microsoft Dynamics NAV Server uses to access SQL Server.
The database roles that the account has will be copied from the original database to the new application database.
If this parameter is not specified, the Export-NAVApplication cmdlet will use the NT AUTHORITY\NETWORK SERVICE account.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String ServerName
The value of the DatabaseServer parameter.

### System.String ServerInstance
The value of the ServerInstance parameter.

### System.String DatabaseName
The value of the DatabaseName parameter.

## NOTES

## RELATED LINKS

[Get-NAVApplication](Get-NAVApplication.md)

[Mount-NAVApplication](Mount-NAVApplication.md)

[Remove-NAVApplication](Remove-NAVApplication.md)
