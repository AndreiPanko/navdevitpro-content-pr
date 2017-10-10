---
author: jswymer
title: "How to: Write Extension Upgrade Code"
ms.custom: na
ms.date: 07/10/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
---

# Upgrading Extensions V2
This topic provides information about how to upgrade an existing extension to a new version. 

Schema changes can only be additive. This allows multiple versions to exist on the same server simultaneously.

## What constitutes an upgrade
An *upgrade* is when you publish an extension that has a higher version number than the current published versions.

Can I define more than one CU with the upgrade triggers?
	- Absolutely! While there is a set order to the sequence of these triggers, there is no guarantee on the order of execution of the different CUs so developers should be aware not rely on it and keep multiple CU's need to be independent of each other.
	
	If I don't need to touch data between versions do I still need to 'upgrade'?
If there are no data changes between the versions of your extension, then you do not need to write upgrade code. All data that is not modified by upgrade code will automatically be restored. 

## Developing an extension for upgrading
When developing a new extension version, you have to consider the data that comes from an old extension version, and determine any modifications that must be applied to the data to make it compatible with the current version. For example, it could be that the new version has a new field that needs default values for existing records or the new version has new tables that must be linked to existing records. To address this type of data handling, you have to a write upgrade code for the extension version.

If there are no data changes between the versions of your extension, then you do not need to write upgrade code. All data that is not modified by upgrade code will automatically be restored. 

### Writing upgrade code

You write upgrade logic in an upgrade codenit, which is a codeunit whose [SubType property] is set to **Upgrade**.  An upgrade codeunit supports several system triggers on which you can add data upgrade code. These triggers are invoked when you run a data upgrade process on the new extension.

### Upgrade triggers
The following tables describes the upgrade triggers and lists them in the order in which they are invoked.

|Trigger |Description | Fails the upgrade on error |
|--------|------------|------------------------|
|OnCheckPreconditionsPerCompany() or OnCheckPreconditionsPerDatabase()| Used to check that certain requirements are met in order for to run the upgrade.|Yes|
|OnUpgradePerCompany() or OnUpgradePerDatabase()|Used to perform the actual upgrade.|Yes| 
|OnValidateUpgradePerCompany() or OnValidateUpgradePerDatabase()|Used to check that the upgrade was successful.|Yes|
|OnAfterUpgradeCommitPerCompany() or OnAfterUpgradeCommitPerDatabase()|Used to perform post-upgrade tasks after transactions in the previous triggers are committed.|No.|

`PerCompany` triggers are run one time for each company in the database, where each trigger is executed within its own system session for the company.

`PerDatabase` triggers are run executed once in the entire upgrade process, in a single system session that does not open any company.

### Upgrade codeunit syntax
The following code illustrates the basic syntax and structure of an upgrade codeunit:

```
codeunit [ID] [NAME]
{
	Subtype=Upgrade;
	
	trigger OnCheckPreconditionsPerCompany()
	begin
		// Code to make sure company is OK to upgrade.
	end;
	
	trigger OnUpgradePerCompany()
	begin
		// Code to perform company related table upgrade tasks
	end;
	
	trigger OnValidateUpgradePerCompany()
	begin
		// Code to make sure that upgrade was successful for each company
	end;
	
	procedure OnAfterUpgradeCommitPerCompany()
	begin
		// Code that performs  company related 'post-commit' tasks
	end;
}
```
> [!TIP]
> Use the shortcuts `tcodunit`and `ttrigger` to create the basic structure for the codeunit and trigger.

## Running the upgrade orto a new extension version

To upgrade to the new extension version, you use the Sync-NAVApp and Start-NAVAppDataUpgrade cmdlets of the [!INCLUDE[nav_admin_md](includes/nav_admin_md.md)] to synchronize table schema changes in the extension with the SQL and run the data upgrade.

1.  Publish the new extension version. This example assumes the extension is not signed, which is not recommend in a production environment.

    ```
    Publish-NAVApp -ServerInstance DynamicsNAV -Path .\ProswareStuff_1.7.1.0.app -SkipVerification
    ```
    This validates the extension syntax against server instance, and stages it for syncing.

3.  Synchronize the new extension version with the database.

    ```
    Sync-NAVApp -ServerInstance NAV -Name ProswareStuff -Version 1.7.1.0
    ```
    This synchronizes any table schema changes in the extension with the SQL database.

4.  Run a data upgrade.

    ```
    Start-NAVAppDataUpgrade -ServerInstance NAV -Name ProswareStuff -Version 1.5.1.0
    ```
    This runs the upgrade logic that is defined by the upgrade codeunits in the extension. The current extension version is uninstalled, and the new extension version is installed.

## See Also  
[Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md)  
[Upgrading Extensions](extensions-upgrading.md)  
[GETARCHIVEVERSION Function](GETARCHIVEVERSION-Function.md)  
[GETARCHIVERECORDREF Function](GETARCHIVERECORDREF-Function.md)  
[RESTOREARCHIVEDATA Function](restorearchivedata-function.md)  
[DELETEARCHIVEDATA Function](deletearchivedata-function.md)  
[How to: Develop an Extension](How-to--Develop-an-Extension.md)  
[How to: Create an Extension Package](How-to--Create-an-Extension-Package.md)  
[Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md)  
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)  
[Development Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=510540)  
[Development](development.md)  
