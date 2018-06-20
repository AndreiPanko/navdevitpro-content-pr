---
title: Update user | Microsoft Docs
description: Updates a user object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: henrikwh

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/15/2018
ms.author: solsen
---

# Patch user
Patches an automationCompany object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
```
PATCH /microsoft/automation/{apiVersion}/companies({companyid})/users({securityId})
```
## Request headers
|Header       |Value                    |
|-------------|-------------------------|
|Authorization|Bearer {token}. Required.|
|Content-Type |application/json         |
|If-Match     |Required. When this request header is included and the eTag provided does not match the current tag on the **user**, the **user** will not be updated.|

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and a **automationCompany** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({id})/automationCompanies
Content-type: application/json
If-Match:*
{
    "displayName": "My Company",
    "evaluationCompany": false
}

```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "id": "2b8ea70b-1384-448d-b3d7-1d26c41f3cec",
    "name": "CRONUS Danmark A/S",
    "evaluationCompany": false,
    "displayName": "My Company",
    "businessProfileId": ""
}
```



## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[AutomationCompany entity](../resources/dynamics_microsoft_automation_automationCompany.md)  
[Get automationCompany](../api/dynamics_microsoft_automation_automationCompanies_get.md)  
[Post automationCompany](../api/dynamics_microsoft_automation_automationCompanies_post.md)  
[Delete automationCompany](../api/dynamics_microsoft_automation_automationCompanies_delete.md)  