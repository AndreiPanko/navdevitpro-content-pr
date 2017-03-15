---
title: GET customer method | Microsoft Docs
description: Gets a customer.
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

# GET Customer Method
Retrieve the properties and relationships of an customers object for Dynamics 365 Financials.

## Prerequisites

## HTTP request

A customer from Dynamics 365 Financials.
```
GET /financials/companies/{id}/customers/{id}
```

## Optional query parameters

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer . Required. |

## Request body

Do not supply a request body for this method.

## Reponse

If successful, this method returns a 200 OK response code and customers object in the response body.

**Request**

Here is an example of the request.

```
GET https://graph.microsoft.com/beta/financials/companies/{id}/customers/{id}
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```
    {
      "id": "e7bf4477-00f0-4cf3-8aea-abfa5a1524f3",
      "number": "10000",
      "displayName": "Coho Winery",
      "address": {
        "street": "192 Market Square",
        "city": "Atlanta",
        "state": "GA",
        "countryLetterCode": "US",
        "postalCode": "31772"
      },
      "phoneNumber": "",
      "email": "jim.glynn@cronuscorp.net",
      "website": "",
      "taxLiable": true,
      "currencyCode": "USD",
      "paymentTerms": {
        "code": "1M(8D)",
        "description": "1 Month/2% 8 days"
      },
      "shipmentMethod": null,
      "paymentMethod": {
        "code": "BANK",
        "description": "Bank Transfer"
      },
      "blocked": " ",
      "balance": 0,
      "lastModifiedDateTime": "2017-03-07T00:35:28.983Z"
    }
```

## See Also
[Microsoft Graph Reference](graph-reference.md)  
