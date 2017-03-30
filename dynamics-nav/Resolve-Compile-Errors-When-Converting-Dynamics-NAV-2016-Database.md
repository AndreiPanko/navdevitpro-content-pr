---
title: "Compilation Errors When Converting a Microsoft Dynamics NAV 2016 Database"
ms.custom: na
ms.date: 20/03/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 6ea75b39-cf7d-4c88-868b-86fa0be2426b
caps.latest.revision: 4
manager: edupont
---
# Resolving Compilation Errors When Converting a Dynamics NAV 2016 Database
When you convert a [!INCLUDE[navcorfu](includes/navcorfu_md.md)] database, you will receive compilation errors in several standard [!INCLUDE[navnow](includes/navnow_md.md)] objects. This article describes how to resolve these errors.

## Compilation Errors
The following table lists the compilation errors that might occur when build the server application objects during the database conversion, with a link to a solution for fixing the problem.

|  Object Type  |  Object ID  |  Object Name  |  Function/Trigger  |  Error Message  |  Solution  |
|---------------|-------------|---------------|--------------------|------------|------------|
|Table|5330|CRM Connection Setup|CreateOrganizationService|You have specified an unknown variable. CrmServiceClient Define the variable under 'Global C/AL symbols'.|See [Resolving Table 5330 CRM Connection Setup Error](Updated-Code-Table5330-CRM-Connection-Setup.md). |
|Codeunit|824|DO Encryption Mgt.|Encrypt|You have specified an unknown variable. KeyExists Define the variable under 'Global C/AL symbols'.|See [Resolving Dynamics Online Payment Service Errors](Resolve-Dynamics-Online-Errors-Database-Conversion.md).|
|Codeunit|826|DO Payment Integration Mgt.|RefreshTransactionStatus|You have specified an unknown variable. Payment Define the variable under 'Global C/AL symbols'.|See [Resolving Dynamics Online Payment Service Errors](Resolve-Dynamics-Online-Errors-Database-Conversion.md).|
|Codeunit|829|DO Payment Trans. Log Mgt.|CompleteTransLogEntry|You have specified an unknown variable. IsSuccess Define the variable under 'Global C/AL symbols'.|See [Resolving Dynamics Online Payment Service Errors](Resolve-Dynamics-Online-Errors-Database-Conversion.md).|
|Codeunit|1410|Doc. Exch. Service Mgt.|Initialize|You have specified an unknown variable. Consumer Define the variable under 'Global C/AL symbols'.|See [Resolving Codeunit 1410 Doc. Exch. Service Mgt. Error](Resolve-CU1410-Doc-Exch-Service-Mgt-Compilation-Error.md).|
|Codeunit|130400|CAL Test Runner|OnBeforeTestRun|The OnBeforeTestRun trigger signature is not valid.|See [Resolving OnBeforeTestRun and OnAfterTestRun Trigger Errors](Resolve-OnBeforeTestRun-OnAfterTestRun-Compile-Errors.md).|
|Codeunit|130400|CAL Test Runner|OnAfterTestRun|The OnAfterTestRun trigger signature is not valid.|See [Resolving OnBeforeTestRun and OnAfterTestRun Trigger Errors](Resolve-OnBeforeTestRun-OnAfterTestRun-Compile-Errors.md).|
|Codeunit|130402|CAL Test Runner|OnBeforeTestRun|The OnBeforeTestRun trigger signature is not valid.|See [Resolving OnBeforeTestRun and OnAfterTestRun Trigger Errors](Resolve-OnBeforeTestRun-OnAfterTestRun-Compile-Errors.md).|
|Codeunit|130402|CAL Command Line Test Runner|OnAfterTestRun|The OnAfterTestRun trigger signature is not valid.|See [Resolving OnBeforeTestRun and OnAfterTestRun Trigger Errors](Resolve-OnBeforeTestRun-OnAfterTestRun-Compile-Errors.md).|

<!--
## <a name="CU1410"></a>Resolving Codeunit 1410 Doc. Exch. Service Mgt. error  
Use the [!INCLUDE[nav_dev_short_md](includes/nav_dev_short_md.md)] to change the **DotNet** data type variables of the local function **Initialize** to the use Microsoft.Dynamics.Nav.OAuth version 10.0.0.0 assembly, as shown in the following table.

|  Variable  |  DatType  |  Subtype  |
|------------|-----------|-----------|
|OAuthAuthorization|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.OAuthAuthorization.'Microsoft.Dynamics.Nav.OAuth, Version=10.0.0.0'|
|OAuthConsumer|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.Consumer.'Microsoft.Dynamics.Nav.OAuth, Version=10.0.0.0'|
|OAuthToken|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.Token.'Microsoft.Dynamics.Nav.OAuth, Version=10.0.0.0'|
-->
<!--
## <a name="TestRunnerTriggers"></a>Resolving OnBeforeTestRun and OnAfterTestRun trigger errors

Use the [!INCLUDE[nav_dev_short_md](includes/nav_dev_short_md.md)] to change the signature of the C/AL OnBeforeTestRun and OnAfterTestRun trigger functions of the test runner codeunits to include the *TestPermissions* parameter.

OnBeforeTestRun trigger before change:
```
OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];) Ok : Boolean)
```
OnBeforeTestRun trigger after change:
```
OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];FunctionTestPermissions : TestPermissions) Ok : Boolean)
```
OnAfterTestRun trigger before change:
```
OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];Success : Boolean)
```
OnAfterTestRun trigger after change:
```
OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];FunctionTestPermissions : TestPermissions;Success : Boolean)
```
If you do not change the signature, you will get errors when you compile these objects.
-->
<!--
## <a name="DOL"></a>Resolving Dynamics Online Payment Service related errors
These errors occur because Dynamics Online Payment Service has been discontinued in [!INCLUDE[nav2017](includes/nav2017.md)]. To resolve these errors and other issues related Dynamics Online Payment Services, replace the codeunits that are listed in the table with mock codeunits that are available from the provided links.

|  Codunit  |  Mock Code  |
|-----------|-------------|
|824|[Mock Code for Codeunit 824 DO Encryption Mgt.](Mock-Code-CU824-DO-Encryption-Mgt.md)|
|825|[Mock Code for Codeunit 825 DO Payment Mgt.](Mock-Code-CU825-DO-Payment-Mgt.md)|
|826|[Mock Code for Codeunit 826 DO Payment Integration Mgt.](Mock-Code-CU826-DO-Payment-Integration-Mgt.md)|
|827|[Mock Code for Codeunit 827 DO Payment Card Validation](Mock-Code-CU827-DO-Payment-Card-Validation.md)|
|829|[Mock Code for Codeunit 829 DO Payment Trans. Log Mgt.](Mock-Code-CU829-DO-Payment-Trans-Log-Mgt.md)|
-->
## See Also  
 [Converting a Database](Converting-a-Database.md)
