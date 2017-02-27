---
title: "Post Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 02/21/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 9
manager: edupont
author: solsen
---

# Post Method
Sends a POST request to the specified Uri as an asynchronous operation.

```
[Ok := ] HttpClient.Post(Path, Content, Reponse)
```

## Parameters
*Path*
Type: String

*Content*
Type: HttpContent

*Response*
Type: HttpResponseMessage

## Return Value
*Ok*
Type: Boolean

**true** if the operation was successful; otherwise, **false**.

## Remarks

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)