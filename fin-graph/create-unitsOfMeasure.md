---
title: CREATE unitsOfMeasure method | Microsoft Docs
description: Creates an unitsOfMeasure.
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

# CREATE unitsOfMeasure Method
Create an unitsOfMeasure in Dynamics 365 Financials.

## Prerequisites

## HTTP request
```
POST /financials/companies/{id}/unitsOfMeasure
```
## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer. Required.    |
|Content-Type  |application/json    |

## Request body

In the request body, supply a JSON representation of unitsOfMeasure object.

## Reponse

If successful, this method returns 201, Created response code and vendunitsOfMeasureors object in the response body.

## Example

**Request**

Here is an example of a request.

```
POST https://graph.microsoft.com/beta/finacials/companies/{id}/unitsOfMeasure
Content-type: application/json

{
  "code": "PCS",
  "displayName": "Piece",
  "internationalStandardCode": "EA"
}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "code": "PCS",
  "displayName": "Piece",
  "internationalStandardCode": "EA",
  "lastModifiedDateTime": "2017-03-15T01:21:09.563Z"
}

```



## See Also
[Microsoft Graph Reference](graph-reference.md)  