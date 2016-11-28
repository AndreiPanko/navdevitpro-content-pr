---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVServerSession

## SYNOPSIS
Returns information about active sessions for a Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVServerSession [-Tenant <TenantId>] [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
Use the Get-NAVServerSession cmdlet to return information about active sessions for a Microsoft Dynamics NAV Server instance.
The following information is returned for each session:
Server Instance ID
Session ID
User SID
Server Instance Name
Server Computer Name
User ID
Client Type
Client Computer Name
Login Datetime
 Database Name

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-NAVServerSession -ServerInstance DynamicsNAV -Tenant default

ServerInstanceID   : 1
                       
SessionID                 : 1
                       
UserSID                   : DE8B398E-C154-45BC-931A-3A74A8AF5A85
                       
ServerInstanceName : DynamicsNAV90
                       
ServerComputerName : MyServer
                       
UserID                    : CRONUSNavUser1
                       
ClientType                : WindowsClient
                       
ClientComputerName : MyComputer
                       
LoginDatetime             : 21-09-2013 13:06:24
                       
DatabaseName              : Demo Database NAV

                       
ServerInstanceID   : 1
                       
SessionID                 : 2
                       
UserSID                   : DE8B398E-C154-45BC-931A-3A74A8AF5A85
                       
ServerInstanceName : DynamicsNAV90
                       
ServerComputerName : MyServer
                       
UserID                    : CRONUSNavUser2
                       
ClientType                : WindowsClient
                       
ClientComputerName : MyOtherComputer
                       
LoginDatetime             : 21-09-2013 10:28:40
                       
DatabaseName              : Demo Database NAV
```

Description

-----------

The example returns a list of all client connections for the Microsoft Dynamics NAV Server instance DynamicsNAV.
The return data shows two Windows client users.

## PARAMETERS

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant that you want to get the active sessions for, such as Tenant1.
This parameter is required unless the specified service instance is not configured to run multiple tenants.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
{{Fill Force Description}}

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

## INPUTS

## OUTPUTS

### System.Data.DataTable

## NOTES
## RELATED LINKS

