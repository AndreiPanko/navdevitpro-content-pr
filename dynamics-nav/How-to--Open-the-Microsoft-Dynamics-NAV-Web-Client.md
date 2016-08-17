---
title: "How to: Open the Microsoft Dynamics NAV Web Client"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 41d64ea9-47da-4184-81b7-a7e98b05d530
caps.latest.revision: 31
manager: terryaus
---
# How to: Open the Microsoft Dynamics NAV Web Client
You open the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] by using a web browser from a device that has a network connection. To open the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)], you must know the name of the computer that is running the [!INCLUDE[nav_web_server](../dynamics-nav/includes/nav_web_server_md.md)] and the HTTP port that it is running on.  
  
 For a list of supported browsers, see [System Requirements for Microsoft Dynamics NAV 2016](../dynamics-nav/System-Requirements-for-Microsoft-Dynamics-NAV-2016.md). For more specific parameters, see [Opening a Page in the Microsoft Dynamics NAV Web Client by Using a URL](../dynamics-nav/Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md)  
  
### To open [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)]  
  
1.  Open the web browser.  
  
    > [!TIP]  
    >  On the computer where the [!INCLUDE[nav_web_server](../dynamics-nav/includes/nav_web_server_md.md)] are installed, you can open the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] directly from **Start** in Windows. In the **Search** box, type **[!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)] Web Client**, and then choose the related link.  
  
2.  In the address box of the browser, type one of the following URLs.  
  
    |To open|URL|Example|  
    |-------------|---------|-------------|  
    |The Role Center for the default company|http:\/\/ComputerName:Port\/WebServerInstance\/WebClient<br /><br /> Or \(for multitenant deployments\)<br /><br /> http:\/\/ComputerName:Port\/WebServerInstance\/WebClient\/default.aspx?tenant\=TenantID|http:\/\/MyNAVWeb:8080\/[!INCLUDE[nav_server_instance](../dynamics-nav/includes/nav_server_instance_md.md)]\/WebClient|  
    |The Role Center for a specific company|http:\/\/ComputerName:Port\/WebServerInstance\/WebClient\/default.aspx?company\=CompanyName<br /><br /> Or<br /><br /> http:\/\/ComputerName:Port\/WebServerInstance\/WebClient\/default.aspx?tenant\=TenantID&company\=CompanyName|http:\/\/MyNAVWeb:8080\/[!INCLUDE[nav_server_instance](../dynamics-nav/includes/nav_server_instance_md.md)]\/WebClient\/default.aspx?company\=CRONUS%20International%20Ltd.|  
    |A specific page|http:\/\/ComputerName:Port\/WebServerInstance\/WebClient\/default.aspx?page\=ID<br /><br /> Or<br /><br /> http:\/\/ComputerName:Port\/WebServerInstance\/WebClient\/default.aspx?tenant\=TenantID&page\=ID|http:\/\/MyNAVWeb:8080\/[!INCLUDE[nav_server_instance](../dynamics-nav/includes/nav_server_instance_md.md)]\/WebClient\/default.aspx?page\=22|  
    |A specific report|http:\/\/ComputerName:Port\/WebServerInstance\/WebClient\/default.aspx?report\=ID<br /><br /> Or<br /><br /> http:\/\/ComputerName:Port\/WebServerInstance\/WebClient\/default.aspx?tenant\=TenantID&report\=ID|http:\/\/MyNAVWeb:8080\/[!INCLUDE[nav_server_instance](../dynamics-nav/includes/nav_server_instance_md.md)]\/WebClient\/default.aspx?report\=5|  
    |A specific profile|http:\/\/ComputerName:Port\/WebServerInstance\/WebClient\/?profile\=ID<br /><br /> Or<br /><br /> http:\/\/ComputerName:Port\/WebServerInstance\/WebClient\/?profile\=ID|http:\/\/MyNAVWeb:8080\/[!INCLUDE[nav_server_instance](../dynamics-nav/includes/nav_server_instance_md.md)]\/WebClient\/?profile\=Small%20Business|  
  
     Substitute the following parameters:  
  
    -   **http** with **https** if SSL is configured for the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] and the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Web Server is not configured to redirect HTTP requests to HTTPS.  
  
    -   **ComputerName** with the name of the computer that is running the [!INCLUDE[nav_web_server](../dynamics-nav/includes/nav_web_server_md.md)].  
  
    -   **Port** with the port number that you configured for the [!INCLUDE[nav_web_server](../dynamics-nav/includes/nav_web_server_md.md)] during installation.  
  
    -   **WebServerInstance** with the virtual directory alias under which the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] application exists on the web server. For more information, see [Microsoft Dynamics NAV Web Server Components Installation on IIS](../dynamics-nav/Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md#WebClientonIIS).  
  
    -   **TenantID** with the name of the tenant that you want to connect to. This parameter is only required when [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] is deployed in a multitenant architecture. The tenant that you specify must be mounted on the [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance that the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] connects to. For more information, see [Multitenant Deployment Architecture](../dynamics-nav/Multitenant-Deployment-Architecture.md).  
  
    -   **CompanyName** with the name of the company in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)]. This parameter is optional and is only needed if you want to open a different company than the one specified in [\($ N\_9176 My Settings $\)](../Topic/\($%20N_9176%20My%20Settings%20$\).md).  
  
    -   **ID** with the ID that is assigned to the page or report object in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)].  
  
    > [!TIP]  
    >  After you open the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)], you can choose the **Search for Page or Report** icon to find pages and reports. The **Search for Page or Report** button in the ribbon.  
  
 For more information about the URLs to open pages and reports, see [Opening a Page in the Microsoft Dynamics NAV Web Client by Using a URL](../dynamics-nav/Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md) and [Opening a Report in the Microsoft Dynamics NAV Web Client by Using a URL](../dynamics-nav/Opening-a-Report-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md).  
  
## See Also  
 [How to: Open the Microsoft Dynamics NAV Tablet or Phone Client from a Browser](../Topic/How%20to:%20Open%20the%20Microsoft%20Dynamics%20NAV%20Tablet%20or%20Phone%20Client%20from%20a%20Browser.md)   
 [Developing for the Microsoft Dynamics NAV Web Client](../dynamics-nav/Developing-for-the-Microsoft-Dynamics-NAV-Web-Client.md)   
 [How to: Install the Web Server Components](../Topic/How%20to:%20Install%20the%20Web%20Server%20Components.md)   
 [How to: Configure SSL to Secure the Connection to Microsoft Dynamics NAV Web Client](../Topic/How%20to:%20Configure%20SSL%20to%20Secure%20the%20Connection%20to%20Microsoft%20Dynamics%20NAV%20Web%20Client.md)