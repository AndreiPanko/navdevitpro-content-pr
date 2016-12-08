---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401397
schema: 2.0.0
---

# Set-NAVServerPermissionSet

## SYNOPSIS
Renames a Microsoft Dynamics NAV permission set.

## SYNTAX

```
Set-NAVServerPermissionSet -PermissionSetId <String> -PermissionSetName <String> [-ServerInstance] <String>
 [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Set-NAVServerPermissionSet cmdlet to change the name of an existing a Microsoft Dynamics NAV permission set.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVServerPermissionSet DynamicsNAV -PermissionSetId Original -NewPermissionSetId Improved
```

This example renames an existing permission set.

## PARAMETERS

### -PermissionSetId
Specifies the existing name (ID) for the permission set.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PermissionSetName
Specifies the name of the permission set.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### System.String
You can pipe a string that contains a Microsoft Dynamics NAV Server instance name to the cmdlet.

## OUTPUTS

### None

## NOTES
## RELATED LINKS

[Get-NAVServerPermissionSet](Get-NAVServerPermissionSet.md)

[New-NAVServerPermissionSet](New-NAVServerPermissionSet.md)

[Remove-NAVServerPermissionSet](Remove-NAVServerPermissionSet.md)

[New-NAVServerPermission](New-NAVServerPermission.md)

[Get-NAVServerPermission](Get-NAVServerPermission.md)

[Remove-NAVServerPermission](Remove-NAVServerPermission.md)

[Set-NAVServerPermission](Set-NAVServerPermission.md)
