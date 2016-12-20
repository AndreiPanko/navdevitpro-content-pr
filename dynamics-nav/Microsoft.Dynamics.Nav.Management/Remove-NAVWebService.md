---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401391
schema: 2.0.0
---

# Remove-NAVWebService

## SYNOPSIS
Removes the specified web services from the application that is mounted against the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Remove-NAVWebService -ObjectType <ObjectType> -ServiceName <String> [-ServerInstance] <String> [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use the Remove-NAVWebService cmdlet to delete the web services that have been created in the application that is mounted against the specified Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVWebService -ServerInstance DynamicsNAV -ServiceName Customer -ObjectType Page
```

This example uses the Remove-NAVWebService cmdlet to remove a web service that is based on a page object and has the name Customer.

## PARAMETERS

### -ObjectType
Specifies the type of the object that the web service exposes. SOAP web services and ODATA web services support Create, Read, Update, and Delete operations for page objects. SOAP web services support codeunit objects. ODATA web services support query objects as read-only. For more information, see "Overview of Microsoft Dynamics NAV Web Services" in the Developer and ITPro documentation for Microsoft Dynamics NAV.

```yaml
Type: ObjectType
Parameter Sets: (All)
Aliases: 
Accepted values: TableData, Table, Form, Report, Dataport, CodeUnit, XmlPort, MenuSuite, Page, Query, System, FieldNumber, LimitedUsageTableData, TablePage, PageExtension, TableExtension

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
The name of the web service that you want to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance. You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NAVWebService](Get-NAVWebService.md)

[New-NAVWebService](New-NAVWebService.md)
