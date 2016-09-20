<properties
                pageTitle="MESSAGE Function (Notification) | Dynamics NAV"
                description="Describes the MESSAGE function of the Notification data type for sending notifications"
                services=""
                documentationCenter=""
                authors="jswymer"/>

<tags
    ms.prod="dynamics-nav-2017"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="06/16/2016"
    ms.author="jswymer" />

# PRODUCTNAME Functions
The PRODUCTNAME functions get the name of the application in three variations: full, marketing, and short.

```
String := PRODUCTNAME.FULL
```
*FULL* returns a text string that contains the application's full name, such as "Microsoft Dynamics NAV".

```
String := PRODUCTNAME.MARKETING
```
*MARKETING* returns a text string that contains the application's marketing name, such as "Microsoft Dynamics NAV 2017".

```
String := PRODUCTNAME.SHORT
```
*SHORT* returns a text string that contains the application's short name, such as "Dynamics NAV".

## Return Value
*String*

Type: Code or text

The product name.

## Remarks
Each application is assigned a full name, marketing name, and short name. These functions are useful when you include the application name in UI text. Instead of using static text for the name, you use one of the PRODUCTNAME functions. This lets you use the same text string across different applications, and makes it easier if the application is ever renamed.
