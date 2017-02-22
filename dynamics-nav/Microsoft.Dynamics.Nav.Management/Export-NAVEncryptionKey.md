---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=518092
schema: 2.0.0
---

# Export-NAVEncryptionKey

## SYNOPSIS
Exports the encryption key to a file in a specified path on the computer or network.

## SYNTAX

```
Export-NAVEncryptionKey [-KeyPath] <String> [-Password <SecureString>] [-ServerInstance] <String> [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
When using SQL Server authentication between the Microsoft Dynamics NAV Server instance and database in SQL Server, Microsoft Dynamics NAV encrypts passwords that are used by a Microsoft Dynamics NAV Server instance to access to Microsoft Dynamics NAV databases in SQL Server.This includes, for example, the Microsoft Dynamics NAV Server service account credentials and the database credentials.

To encrypt and decrypt the passwords, an encryption key is used. Microsoft Dynamics NAV uses a single encryption key per server instance. The same encryption must be included in the Microsoft Dynamics NAV database to which the server instance connects.

In some cases, such as when you upgrade or migrate a system from one set of hardware to another, you might need to copy of the encryption key to use it on another Microsoft Dynamics NAV Server instance.

By using the Export-NAVEncryptionKey cmdlet, you can export the encryption key from one Microsoft Dynamics NAV Server instance to a file, and then use the Import-NAVEncryptionKey cmdlet to import the exported key into another Microsoft Dynamics NAV Server instance.
The Export-NAVEncryptionKey cmdlet enables you to specify a destination file for the key and specify a password to protect the file.

## EXAMPLES

### EXAMPLE 1
```
Export-NAVEncryptionKey -ServerInstance DynamicsNAV -KeyPath "C:\Keys\nav.key" -Password (Get-Credential).Password
```

The example exports an encryption key from a Microsoft Dynamics NAV Server instance to a password protected file.

### EXAMPLE 2
```
Export-NAVEncryptionKey -ServerInstance DynamicsNAV -KeyPath "C:\Keys\nav.key" | Import-NAVEncryptionKey -ServerInstance NewInstance
```

The example exports an encryption key from a Microsoft Dynamics NAV Server instance, and then imports that key into another Microsoft Dynamics NAV Server instance on the same computer.

## PARAMETERS

### -KeyPath
Specifies the full path to where the key file will be exported.
The full path includes the drive, folders, and file name.
The folder path must already exist.
The file will be created that has the given file name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies a password that protects the encryption key file.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String KeyPath
Returns the value of the KeyPath parameter.

## NOTES

## RELATED LINKS

[Import-NAVEncryptionKey](Import-NAVEncryptionKey.md)
