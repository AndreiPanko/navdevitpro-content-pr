---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVWebServerInstance

## SYNOPSIS
Gets the information about the Microsoft Dynamics NAV Web Server instances that are registered on a computer.

## SYNTAX

```
Get-NAVWebServerInstance [[-WebServerInstance] <String>] [-Force]
```

## DESCRIPTION
You can use Get-NAVWebServerInstance cmdlet to get the following information about Microsoft Dynamics NAV Web Server instances that are registered in IIS on the computer.
WebServerInstance: The name of the Microsoft Dynamics NAV Web Server instance
Uri: Unified Resource Locator of web server instance.
Server: The computer that is running the Microsoft Dynamics NAV Server that the Microsoft Dynamics NAV Web Server instance connects to.
ServerInstance: The Microsoft Dynamics NAV Server instance that the Microsoft Dynamics NAV Web Server instance connects to.
ClientServicesPort: Specifies the listening TCP port for the Microsoft Dynamics NAV Server instance that the Microsoft Dynamics NAV Web Server instance connects to.
Company: The Microsoft Dynamics NAV company that is configured in the web.config file
DNSIdenity: Specifies the subject name or common name of the service certificate for Microsoft Dynamics NAV Server instance.
This parameter is only relevant when the ClientServicesCredentialType in the Microsoft Dynamics NAV Server instance configuration is set to UserName, NavUserPassword, or AccessControlService, which requires that security certificates are used on the Microsoft Dynamics NAV Web client and Microsoft Dynamics NAV Server to protect communication.
ACSUri: Specifies the Unified Resource Identifier of the authentication page when using Windows Azure Access Control Service (ACS) or Windows Azure Active Directory (Windows Azure AD) to authenticate users.
This parameter is only relevant when the ClientServicesCredentialType in the Microsoft Dynamics NAV Server instance configuration is set to AccessControlService.
Language: Sets the language version of the Microsoft Dynamics NAV Web client.
ReqionFormat: Specifies the culture name that is used to format dates, times, numbers, and currency in the Microsoft Dynamics NAV Web client.
Configuration file: The location of the web.config file that is used by the Microsoft Dynamics NAV Web Server instance.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-NAVWebServerInstance -WebServerInstance DynamicsNAV
```

Description

-----------

This example gets information about the Microsoft Dynamics NAV Web Server instance that is named DynamicsNAV.

## PARAMETERS

### -WebServerInstance
Specifies the name of the Microsoft Dynamics NAV Web Server instance that you want information about.
If you omit this parameter, then the cmdlet returns information about all Microsoft Dynamics NAV Web Server instances.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

### System.Data.DataRow

## NOTES
## RELATED LINKS

