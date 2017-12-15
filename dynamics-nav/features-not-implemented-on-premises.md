---
title: Features not implemented in on-premises deployments
author: edupont04
manager: edupont
ms.author: edupont
ms.custom: na
ms.date: 12/14/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
---
# Features not implemented in [!INCLUDE[navnowlong](includes/navnowlong_md.md)]

This topic lists features that are not available in [!INCLUDE[navnowlong](includes/navnowlong_md.md)] but are available in [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]. The topic is divided into two sections:
- The first section lists features that are available under very specific circumstances in on-premises deployments.  
- The second section lists features that are not intended for use with on-premises deployments. There are no plans to implement these features.  

## Features that require specific circumstances
The following features are not available in all on-premises deployments because they require specific circumstances.  

| **Feature**                      |**Description**                                  |
|----------------------------------|-------------------------------------------------|
| Read/write data with Excel add-in       |The Excel add-in that enables update of data requires Azure Active Directory as the authentication mechanism. |
| Excel financial reports        |The Excel add-in that is used with the predefined Excel-based financial reports requires Azure Active Directory as the authentication mechanism. |
|Coversheets for contact management|The integration with Word to create the coversheets requires Azure Active Directory as the authentication mechanism.|
| Built-in Power BI reports and charts       |The integration with Power BI requires Azure Active Directory as the authentication mechanism. |
| Built-in Microsoft Flow Management |The integration with Microsoft Flow requires Azure Active Directory as the authentication mechanism.|
| Built-in web services |A number pages and queries are exposed as web services. However, the default endpoint must be manually updated before the web services can be consumed.|
| Outlook add-in |The Outlook add-in requires Dynamics NAV User/Password or Azure Active Directory as the authentication mechanism. |
|Standard REST API|[!INCLUDE[navnowlong](includes/navnowlong_md.md)] contains new standard REST APIs, just as [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]. However, on-premises deployments cannot be reached through Microsoft Graph or the common endpoint *api.financials.dynamics.com*. Instead, you must connect directly to the on-premises deployment, just as when you connect to web services.|

## Features not intended for use in on-premises deployments
The following features are not intended for use in on-premises deployments. There are no plans to implement these features in on-premises deployments.

| **Feature**                      |**Description**                                  |
|----------------------------------|-------------------------------------------------|
| Help mapping       |Online deployments of [!INCLUDE[d365fin](includes/d365fin_md.md)] use a system table to look up Help on the docs.microsoft.com site. This is not supported for on-premises deployments, where only Help Server is supported.|
|In-product search in Help| In online deployments of [!INCLUDE[d365fin](includes/d365fin_md.md)], you can extend an in-product search to also search in help content on the docs.microsoft.com site. This is not supported for on-premises deployments, where only Help Server is supported.|
|Inviting the external accountant|Integration with [!INCLUDE[d365acc_long](includes/d365acc_long_md.md)] is not supported in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].|
|Bulk Invoicing from Microsoft Bookings|Integration with the Bookings app in Office Business Premium is not supported.|
|Create Workflow from Flow|Microsoft Flow does not integrate with on-premises workflow functionality.|
|Yodlee bank feeds|Microsoft does not provide Yodlee bank feeds for [!INCLUDE[navnowlong](includes/navnowlong_md.md)].|
|Sandbox environments|The sandbox environment that you can use to develop extensions against for the new developer experience cannot connect to an on-premises deployment.|


## See Also
[Configuring Microsoft Dynamics NAV](Configuring-Microsoft-Dynamics-NAV.md)  
[How to: Create a Sandbox Environment](/dynamics365/financials/across-how-create-sandbox-environment?toc=/dynamics-nav/toc.json)  