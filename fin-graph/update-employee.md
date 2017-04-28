---
title: UPDATE employee method | Microsoft Docs
description: Updates an employee.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/13/2017
ms.author: solsen
---

# PATCH Employee Method
Update the properties of an employee object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].


## HTTP request

```
PATCH /financials/companies/{id}/employees/{id}
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |
|Content-Type   |application/json. |
|If-Match       |Required. When this request header is included and the eTag provided does not match the current tag on the employee, the employee will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated employee object in the response body.

## Example

**Request**

Here is an example of the request.

```json
PATCH https://graph.microsoft.com/beta/financials/companies/{id}/employees{id}
Content-type: application/json

{
  "givenName": "Anthony",
  "phoneNumber": "0678-8712-3455"
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "number": "TS",
  "displayName": "Anthony Sneath",
  "givenName": "Anthony",
  "middleName": "",
  "surname": "Sneath",
  "jobTitle": "Production Assistant",
  "address": {
    "street": "66B James Road",
    "city": "London",
    "state": "",
    "countryLetterCode": "",
    "postalCode": "N12 5XY"
  },
  "phoneNumber": "0678-8712-3455",
  "mobilePhone": "1234-6545-8799",
  "email": "",
  "personalEmail": "ts@cronus-demosite.com",
  "employmentDate": "1996-03-01",
  "terminationDate": "0001-01-01",
  "birthDate": "1963-12-07",
  "picture@odata.mediaReadLink": "https://graph.microsoft.com/beta/financials/companies/{id}/employees/{id}/picture",
  "lastModifiedDateTime": "2017-03-16T14:57:19.497Z" 
}
```


## See Also
[Microsoft Graph Reference](graph-reference.md)  