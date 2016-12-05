---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=616074
schema: 2.0.0
---

# New-NAVAppManifestFile

## SYNOPSIS
Creates a file with metadata for a NAV App package.

## SYNTAX

```
New-NAVAppManifestFile [-Path] <String> [-Manifest] <NavAppManifest> [-PassThru] [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the New-NAVAppManifestFile cmdlet to create a file with metadata for a NAV App package.

## EXAMPLES

### Example 1
```
New-NavAppManifest -Name "Proseware SmartApp" -Publisher "Proseware, Inc." -Description "First NAV App by Proseware" | New-NavAppManifestFile -Path ".\Manifest-Proseware SmartApp.xml" -Force
```

This example creates an in-memory manifest and then writes it to disk.
The -Force parameter will overwrite the file if it already exists.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation to overwrite an existing manifest file at the given path.

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

### -Manifest
Specifies the manifest object to write to file.
You can pass this object from the New-NAVAppManifest or Get-NAVAppManifest cmdlets to the New-NAVAppManifestFile cmdlet.

```yaml
Type: NavAppManifest
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns the path to the manifest file.

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

### -Path
Specifies the path to the NAV App manifest file to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
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
[Get-NAVAppManifest](Get-NAVAppManifest.md)

[New-NavAppManifest](New-NAVAppManifest.md)  

[Set-NAVAppManifest](Set-NAVAppManifest.md)
