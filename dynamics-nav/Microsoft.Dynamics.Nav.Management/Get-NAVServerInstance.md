---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401360
schema: 2.0.0
---

# Get-NAVServerInstance

## SYNOPSIS
Gets service details for the specified Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVServerInstance [[-ServerInstance] <String>] [-AsXml] [-Force] [<CommonParameters>]
```

## DESCRIPTION
Use the Get-NAVServerInstance cmdlet to obtain service details for the specified Microsoft Dynamics NAV Server instance.

If no Microsoft Dynamics NAV Server instance is specified, then the cmdlet obtains service details for all Microsoft Dynamics NAV Server instances on the server computer.
The service details include the name of the instance (for example, MicrosoftDynamicsNavServer$DynamicsNAV), the display name (for example, Microsoft Dynamics NAV Server \[DynamicsNAV\]), the state of the instance (Running or Stopped), the Service Account (that is, the account that the Microsoft Dynamics NAV Server uses for its credentials), the Microsoft Dynamics NAV Server version (such as 7.0.33571.0), and whether the instance is the default Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
Get-NavServerInstance MyInstance

Name           : MicrosoftDynamicsNavServer$MyInstance
DisplayName    : Microsoft Dynamics NAV Server [MyInstance]
State          : Running
ServiceAccount : NT AUTHORITY\NETWORK SERVICE
Version        : 7.1.33544.0
Default        : False
```

This example returns status information for the MyInstance Microsoft Dynamics NAV Server instance.

## PARAMETERS

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -AsXml
Formats the cmdlet output as an XML document.

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

### System.Xml.XPathNodeList
Returns the Microsoft Dynamics NAV Server instances as well-formatted text.

### System.Xml.XmlDocument
If you use the AsXml parameter, then the cmdlet returns the Microsoft Dynamics NAV Server instances as an XML document

## NOTES

## RELATED LINKS

[New-NAVServerInstance](New-NAVServerInstance.md)

[Remove-NAVServerInstance](Remove-NAVServerInstance.md)

[Set-NAVServerInstance](Set-NAVServerInstance.md)
