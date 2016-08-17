---
title: "How to: Add a Microsoft Dynamics NAV Web Server Instance"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: dc7646f1-c449-4281-af5d-8bb95ff33b08
caps.latest.revision: 10
---
# How to: Add a Microsoft Dynamics NAV Web Server Instance
This topic describes how to use the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Administration Shell to add a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] web server instance on a computer or virtual machine. The [!INCLUDE[nav_shell](../dynamics-nav/includes/nav_shell_md.md)] includes the [T:Microsoft.Dynamics.Nav.Management.Cmdlets.New\-NAVWebServerInstance](assetId:///T:Microsoft.Dynamics.Nav.Management.Cmdlets.New-NAVWebServerInstance) cmdlet that creates an application on IIS for the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)].  
  
### To add a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] web server instance  
  
1.  On the computer or virtual machine that is running [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)], run **[!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Administration Shell** as an Administrator.  
  
    1.  Choose **Start**, in the **Search** box, type **[!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Administration Shell**.  
  
    2.  Right\-click the related link, and then choose **Run as Administrator**.  
  
2.  At the command prompt, type the following command:  
  
    ```  
    New-NAVWebServerInstance -WebServerInstance <MyWebApp> -Server <NAVServer> -ServerInstance <NAVServerInstance> -ClientServicesCredentialType <NAVCredentialType>  
    ```  
  
     Change the following parameter values.  
  
    |Parameter|[!INCLUDE[bp_tabledescription](../dynamics-nav/includes/bp_tabledescription_md.md)]|  
    |---------------|---------------------------------------|  
    |*\<MyWebApp\>*|Specifies the name that you want to give the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] application instance. This name will become part of the URL for the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] application, for example, http:\/\/MyWebServer:8080\/MyWebApp\/WebClient.|  
    |*\<NAVServer\>*|Specifies the name of the computer that is running the [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] to connect the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] web server to.|  
    |*\<NAVServerInstance\>*|Specifies the name of the [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance to connect the web server instance to.|  
    |*\<NAVCredentialType\>*|Specifies the credential type that is configured for the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] and [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)]. Valid options are **NavUserPassword**, **Windows**, **UserName**, and **AccessControlService**. The default value is **NavUserPassword**. **Important:**  The credential type must match the credential type that is used by the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] web server to authenticate [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] users. For more information, see [Configuring the Credential Type on the Microsoft Dynamics NAV Web Client Web Site](../Topic/How%20to:%20Configure%20Authentication%20of%20Microsoft%20Dynamics%20NAV%20Web%20Client%20Users.md#WebClient).|  
  
    > [!NOTE]  
    >  The command that is shown includes only the required parameters of the NAVWebServerInstance cmdlet. The cmdlet has several other parameters that can be used to configure the web server instance. For more information about the syntax and parameters, see [T:Microsoft.Dynamics.Nav.Management.Cmdlets.New\-NAVWebServerInstance](assetId:///T:Microsoft.Dynamics.Nav.Management.Cmdlets.New-NAVWebServerInstance) cmdlet topic in the Administration Cmdlets for [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] section of the Technical Reference.  
  
3.  Press Enter to run the cmdlet.  
  
     A new [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] web server instance with the specified name is added to the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] site on IIS.  
  
    > [!NOTE]  
    >  If you want to change the configuration of the new [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] web server instance after it has been added, modify the web.config file. For more information, see [Configuring Microsoft Dynamics NAV Web Client by Modifying the Web.config File](../dynamics-nav/Configuring-Microsoft-Dynamics-NAV-Web-Client-by-Modifying-the-Web.config-File.md).  
  
## Example  
 This example creates a new [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] web server instance that is named MyNavApp. The [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] web server instance connects to the [!INCLUDE[nav_server_instance](../dynamics-nav/includes/nav_server_instance_md.md)] server instance on the MyNavServer computer.  
  
```  
New-NAVWebServerInstance -WebServerInstance MyNavApp –Server MyNavServer –ServerInstance nav_server_instance –Company MyNavCompany -ClientServicesCredentialType NavUserPassword  
```  
  
 To open the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] for this example, open the following URL in a web browser:  
  
 **http:\/\/mymachine.cloudapp.net\/MyNavApp**  
  
## See Also  
 [Scaling the Microsoft Dynamics NAV Network Topology](../dynamics-nav/Scaling-the-Microsoft-Dynamics-NAV-Network-Topology.md)   
 [Deploying the Microsoft Dynamics NAV Web Server Components](../dynamics-nav/Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [How to: Set Up Multiple Web Server Instances for the Microsoft Dynamics NAV Web Client](../Topic/How%20to:%20Set%20Up%20Multiple%20Web%20Server%20Instances%20for%20the%20Microsoft%20Dynamics%20NAV%20Web%20Client.md)   
 [Deploying and Managing Microsoft Dynamics NAV on Microsoft Azure](../dynamics-nav/Deploying-and-Managing-Microsoft-Dynamics-NAV-on-Microsoft-Azure.md)   
 [How to: Add a Microsoft Dynamics NAV Server Instance](../Topic/How%20to:%20Add%20a%20Microsoft%20Dynamics%20NAV%20Server%20Instance.md)   
 [How to: Add a Microsoft Dynamics NAV Database](../Topic/How%20to:%20Add%20a%20Microsoft%20Dynamics%20NAV%20Database.md)   
 [How to: Add a Microsoft Dynamics NAV Company](../Topic/How%20to:%20Add%20a%20Microsoft%20Dynamics%20NAV%20Company.md)