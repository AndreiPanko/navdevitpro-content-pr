﻿---
title: "Walkthrough: Customizing Microsoft Dynamics CRM Integration in Dynamics NAV"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0658548b-3a7b-4e9a-bd1a-d58c625bd0de
caps.latest.revision: 12
manager: edupont
---
# Walkthrough: Customizing Microsoft Dynamics CRM Integration in Dynamics NAV
This walkthrough introduces customizing the integration of [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] and [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)]. The walkthrough will guide you through setting up integration of campaigns in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] and campaigns in [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)].  
  
 The customization in this walkthrough is done entirely in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)], and does not describe how to modify your [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] solution, such as adding or modify entities and forms.  
  
## Prerequisites  
 To complete this walkthrough, you will need:  
  
-   [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)], including the following:  
  
    -   Campaign entity.  
  
    -   URL of the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Server.  
  
    -   User name and password of a user account that has full permissions to add and modify entities.  
  
-   [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)], including the following:  
  
    -   [!INCLUDE[demolong](../dynamics-nav/includes/demolong_md.md)].  
  
    -   [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] integration enabled, including the default synchronization setup and a working connection from [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] to [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)].  
  
         For more information, see [How to: Set Up a Microsoft Dynamics CRM Connection](../Topic/How%20to:%20Set%20Up%20a%20Microsoft%20Dynamics%20CRM%20Connection.md).  
  
    -   [!INCLUDE[nav_dev_long](../dynamics-nav/includes/nav_dev_long_md.md)].  
  
    -   [!INCLUDE[nav_dev_shell](../dynamics-nav/includes/nav_dev_shell_md.md)].  
  
## About This Walkthrough  
 This walkthrough illustrates the following tasks:  
  
-   Creating an integration table object in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] for mapping a [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity to a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] record type \(table\).  
  
-   Using a [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] integration table as source of a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] page to display [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity records.  
  
-   Creating a page for coupling [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity records to [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] table records.  
  
-   Creating an integration table and field mappings between a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] table and an integration table for [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity.  
  
-   Using events to develop custom code to transform data when synchronizing between [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] and [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)].  
  
## Creating an Integration Table in Dynamics NAV for the Dynamics CRM Entity  
 To integrate data from [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity into [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)], you must create a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] table object that is based on the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity, and then import the new table into the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] database. For this walkthrough, you will create a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] table object for the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)]**Campaign** entity. This table describes the schema of the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] database. The table can contain all or some of the fields from the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity. However, if you intend to write back to [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)], you should include all fields in the table.  
  
 Apart from creating a table object for the entity, you must also create a table object for any relationships that the entity has. For example, the **Campaign** entity has a relationship to the **ModifiedOn** and **CreatedBy** fields of the **Systemuser** entity. Therefore, you will also have to create a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] table for this entity as well. However, the default [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] integration in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] already includes the integration table **5340 CRM Systemuser** for the **Systemuser** entity. Therefore, you will only have to create the table object for the **Systemuser** entity to establish the relationships; you do not have to import this table into the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] database.  
  
#### To create the integration table for the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Campaign entity  
  
1.  Open the [!INCLUDE[nav_dev_shell](../dynamics-nav/includes/nav_dev_shell_md.md)].  
  
2.  At the command prompt, run the New\-NAVCrmTable cmdlet as shown in the following example. Include parameters that specify the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Server URL, the logical names of the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)]**Systemuser** and **Campaign** entities, the ID and name of the corresponding business data table objects in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)], and the path in which to store the generated text files for the table objects.  
  
    ```  
    New-NAVCRMTable – CRMServer MyOrg.Crm4.Dynamics.Com –EntityLogicalName systemuser,campaign –ObjectId 5340,50001 –Name “CRM Systemuser”,“CRM Campaign” –OutputPath c:\CRMObjects  
    ```  
  
     Replace *CRMServerMyOrg.Crm4.Dynamics.Com* with the URL to your [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Server. Replace *c:\\CRMObjects* with the path on your computer or network where you want to save the .txt files for the created tables.  
  
3.  When prompted, enter credentials of the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] user account.  
  
     The process for creating the tables starts. When the process is completed, the output path contains the files TAB5342.txt and TAB50001.txt. The TAB50001.txt contains the description of the integration table **50001 CRM Campaign**. These tables are set to the type **CRM**, as specified by the [TableType Property](../dynamics-nav/TableType-Property.md).  
  
4.  In the [!INCLUDE[nav_dev_long](../dynamics-nav/includes/nav_dev_long_md.md)], import the TAB50001.txt into the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] database to add the integration table **50001 CRM Campaign**, and then compile the new object.  
  
     You can compile the object by using the [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)] or by using finsql.exe. For more information, see [Importing and Exporting Objects](../dynamics-nav/Importing-and-Exporting-Objects.md).  
  
## Creating a Page for Displaying Dynamics CRM Data  
 For scenarios where you want to view BROKEN-INCLUDE-crm](../dynamics-nav/includes/crm_md.md)] data for a specific entity, you can create a page object that uses the integration table for the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity as its source. For example, you might want to have a page that displays a list of the current records in a [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity. In this walkthrough, you will create a list page that uses table [!INCLUDE[50001 CRM Campaigns as its source.  
  
#### To create a list page to display Dynamics CRM campaigns  
  
1.  In [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)], add a new List page.  
  
2.  Set the source table to the integration table **50001 CRM Campaign**.  
  
3.  Add the table fields that you want to display on the page.  
  
4.  Save and compile the page. For purposes of this walkthrough, give the page the name **CRM Campaign List** and ID **50001**.  
  
5.  Run the page to view the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] campaign list.  
  
## Enabling Coupling between Dynamics CRM Campaigns and Dynamics NAV Campaigns  
 To establish a relationship between a Dynamics NAV table record and a Dynamics CRM entity record, you create a coupling. A coupling consists of the primary ID \(typically a GUID\) from Dynamics CRM record and the Integration ID \(GUID\) from Dynamics NAV.  
  
 To enable users to create couplings between records in the two systems, you implement a coupling page in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] for the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity. The coupling page provides the user interface that users can use to couple a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] record to a [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] record. The default [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] integration includes several coupling pages. To create a coupling page for [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Campaigns, you will use page **5241 CRM Coupling Customer** and adapt it the campaign integration. The coupling page that you set up will use the integration table **50001 CRM Campaign** to retrieve campaign data from [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)]. It will use page **50001 CRM Campaign List** that you created previously to display a list of the campaigns from which to choose.  
  
 Before you create the coupling page, you must enable integration records for [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] table that will be used for integration with [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)], in this case, table **5071 Campaign**. After you create the coupling page, you will add actions on the campaign card and list pages that open the coupling page. You will also have to modify codeunit **5331 CRM Coupling Management**.  
  
#### To enable integration records on the Dynamics NAV Campaign table  
  
1.  In [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)], open codeunit **5150 Integration Management**.  
  
2.  In the **IsIntegrationRecord** trigger, add the code `DATABASE::Campaign` to the database list as illustrated in the following code example:  
  
    ```  
    EXIT(TableID IN  
      [DATABASE::Campaign,  
       DATABASE::Resource,  
       DATABASE::"Payment Terms",  
       DATABASE::"Shipment Method",  
    ...  
  
    ```  
  
3.  In the **SetupIntegrationTables** trigger, add the following line of code at the end:  
  
    ```  
    InitializeIntegrationRecords(DATABASE::Campaign);  
    ```  
  
4.  Restart the [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance.  
  
     For more information, see [How to: Start, Stop, Restart, or Remove a Microsoft Dynamics NAV Server Instance](../Topic/How%20to:%20Start,%20Stop,%20Restart,%20or%20Remove%20a%20Microsoft%20Dynamics%20NAV%20Server%20Instance.md).  
  
 When changes occur in the table **5071 Campaign**, an integration record will be created or updated with a timestamp. You can now use the table to create a page for coupling [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] records with [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] records.  
  
#### To create coupling page for campaigns  
  
1.  In [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)], open the page **5241 CRM Coupling Customer** in Page Designer.  
  
     Because the coupling pages contain a lot of logic in C\/AL code, you will use a copy of this page as a starting point for creating the coupling page for campaigns.  
  
2.  Save and compile the page as a new page that has the ID **50002** and the name **CRM Coupling Campaign**.  
  
3.  Change the page's source table to table **5071 Campaign**.  
  
4.  Open the [\($ S\_10204 C\-AL Globals $\)](../dynamics-nav/-$-S_10204-C-AL-Globals-$-.md) window and change all variables, text constants, and functions that reference *CRM Account* to reference *CRM Campaign* instead. For record type variables, this means changing the name and setting the subtype to point to the integration table **50001 CRM Campaign**. The following table includes the required changes.  
  
    ||Current setting|New setting|  
    |-|---------------------|-----------------|  
    |Variable|Name: CRMAccount<br /><br /> Subtype: CRM Account|Name: CRMCampaign<br /><br /> Subtype: CRM Campaign|  
    ||Name: OriginalCRMAccount<br /><br /> Subtype: CRM Account|Name: OriginalCRMCampaign<br /><br /> Subtype: CRM Campaign|  
    ||Name: OriginalCRMAccount<br /><br /> Subtype: CRM Account|Name: OriginalCRMCampaign<br /><br /> Subtype: CRM Campaign|  
    ||Name: SavedCRMAccount<br /><br /> Subtype: CRM Account|Name: SavedCRMCampaign<br /><br /> Subtype: CRM Campaign|  
    |Text Constants|Name: NoSuchCRMRecordErr<br /><br /> ConstValue: Account with name %1 does not exist in [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)].|Name: NoSuchCRMRecordErr<br /><br /> ConstValue: Campaign with name %1 does not exist in [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)].|  
    |Functions|Name: HandleNewCRMAccount|Name: HandleNewCRMCampaign|  
  
5.  In Page Designer, follow these steps:  
  
    1.  In the **Dynamics NAV** group control, change the field that has the SourceExpr **Name** to have the SourceExpr **Description** and change its caption from **Customer** to **Campaign**.  
  
    2.  In the **Dynamics CRM** group, change the field that has the SourceExpr **CRMAccount.Name** to have the SourceExpr **CRMCampaign.Name**, and change its caption from **Account** to **Campaign**.  
  
    3.  Rename the **Dynamics NAV Customer** group to **Dynamics NAV Campaign** and replace the fields in the group with fields from the Campaign table \(ID 5071\). These fields will help users compare the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] record and the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] record.  
  
    4.  Rename the **Dynamics CRM Account** group to **Dynamics CRM Campaign** and replace the fields in the group with fields from the **CRMCampaign** variable that match fields in the **Dynamics NAV Campaign** group.  
  
6.  Open the C\/AL code, and follow these steps to change all references to [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] accounts with references to [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] campaigns:  
  
    1.  Change the local variables on the following triggers. For record type variables, you change the name and set the subtype to point to the integration table **50001 CRM Campaign**.  
  
        |Trigger|Current variable|New variable|  
        |-------------|----------------------|------------------|  
        |CRM Campaign Name \- OnValidate|Name: ManualCRMAccount<br /><br /> Subtype: CRM Account|Name: ManualCRMCampaign<br /><br /> Subtype: CRM Campaign|  
        ||Name: PreviouslySelectedCRMAccount<br /><br /> Subtype: CRM Account|Name: PreviouslySelectedCRMCampaign<br /><br /> Subtype: CRM Campaign|  
        ||Name: CRMAccountFound|Name: CRMCampaignFound|  
        |CRM Campaign Name \- OnLookup|Name: PreviouslySelectedCRMAccount<br /><br /> Subtype: CRM Account|Name: PreviouslySelectedCRMCampaign<br /><br /> Subtype: CRM Campaign|  
        ||Name: CRMAccountList<br /><br /> Subtype: CRM Account|Name: CRMCampaignList<br /><br /> Subtype: CRM Campaign List \(ID 50001\)|  
  
    2.  Remove calls to **SetCurrentlyCoupledCRMAccount**.  
  
         This function call is originally used for color\-coding the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Account list, but you will not implement color coding in this example.  
  
    3.  Replace all references to *CRMAccount* with references to *CRMCampaign*.  
  
    4.  Replace all references to *AccountId* with *CampaignId*.  
  
7.  Save and compile the page.  
  
 The coupling page can now be used to create a link between a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] campaign record and a [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] campaign record. To give users access to this page, the next step is to add actions that open the coupling page from the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] campaign card page.  
  
#### To create actions on the campaign page for managing the coupling  
  
1.  Open page **5086 Campaign Card** in Page Designer, and then open Action Designer.  
  
     For more information about how to add actions, see [How to: Add Actions to a Page](../Topic/How%20to:%20Add%20Actions%20to%20a%20Page.md).  
  
2.  Add an **ActionGroup** control that is caption **Dynamics CRM**.  
  
3.  Add another **ActionGroup** control under **Dynamics CRM** that has the caption **Coupling**.  
  
4.  In the **Coupling** action group, add the following actions:  
  
    |Name|Caption|  
    |----------|-------------|  
    |ManageCRMCoupling|Manage Coupling|  
    |DeleteCRMCoupling|Delete Coupling|  
  
5.  Open the C\/AL code for the actions, and follow these steps:  
  
    1.  In the code for the action `ManageCRMCoupling`, add a local variable that has name **CRMIntegrationManagement** and references codeunit **5330 CRM Integration Management** as its subtype, and then add the following line of code:  
  
        ```  
        CRMIntegrationManagement.CreateOrUpdateCoupling(RECORDID);  
        ```  
  
    2.  In the code for the action `DeleteCRMCoupling`, add a local variable that has the name **CRMCouplingManagement** and references codeunit **5331 CRM Coupling Management** as its subtype, and then add the following line of code:  
  
        ```  
        CRMCouplingManagement.RemoveCoupling(RECORDID);  
  
        ```  
  
6.  Save and compile the page.  
  
 The coupling page is now available from the Campaign page. The next step is to modify codeunit **5331 CRM Coupling Management** to include a function that performs the coupling operation.  
  
#### To modify codeunit 5331 CRM Coupling Management  
  
1.  Open codeunit **5331 CRM Coupling Management** in Codeunit Designer.  
  
2.  Create a new local function that is called **CreateOrUpdateCouplingCampaign**. Design the function based on the existing coupling function **CreateOrUpdateCouplingCustomer**, replicating the parameters, variables, and return values, except with the following differences:  
  
    1.  Change the page variable **CRMCouplingCustomer** to *CRMCouplingCustomer* and set the Subtype to the new campaign coupling page **50002 CRM Coupling Campaign**.  
  
    2.  Change the record variable **Customer** to *Campaign* and set the Subtype to the table **5071 Campaign**.  
  
    3.  Copy the code from the `CreateOrUpdateCouplingCustomer`, and replace all references to `Customer` with `Campaign`.  
  
3.  In the `CreateOrUpdateCoupling` function, add a `Case` for the **Campaign** table as follows:  
  
    ```  
    CASE RecordID.TABLENO OF  
      DATABASE::Campaign:  
        EXIT(CreateOrUpdateCouplingCampaign(RecordID,CRMID,CreateNew,Synchronize,Direction));  
    ...  
  
    ```  
  
4.  Save and compile the codeunit.  
  
 The coupling between [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Campaigns and [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Campaigns is complete, and users can configure the coupling by using the new actions and coupling page.  
  
 To enable users to open the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Campaign record from the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Campaign, the next step is to add an additional action to the Campaign Card page.  
  
#### To add actions to open the Dynamics CRM campaign record  
  
1.  Open page **5086 Campaign Card** in Page Designer, and then open Action Designer.  
  
2.  In the **Dynamics CRM** action group, before the **Coupling** action, add a new action that has the name **GotoCRMCampaign** and caption **Campaign**.  
  
3.  In the C\/AL code for the action, add a variable that has the name **CRMIntegrationManagement** and references codeunit **5330 CRM Integration Management**, and then add the following line of code:  
  
    ```  
    CRMIntegrationManagement.ShowCRMEntityFromRecordID(RECORDID);  
  
    ```  
  
4.  Save and compile the card page.  
  
5.  Open codeunit **5334 CRM Setup Defaults** in Codeunit Designer.  
  
6.  Add the following code to the `GetTableIDCRMEntityNameMapping` function to add an entity table mapping for table **5081 Campaign** and integration table **50001 CRM Campaign**:  
  
    ```  
    AddEntityTableMapping('campaign',DATABASE::Campaign,TempNameValueBuffer);  
    AddEntityTableMapping('campaign',DATABASE::"CRM Campaign",TempNameValueBuffer);  
  
    ```  
  
7.  Save and compile the codeunit.  
  
 The coupling and links between [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Campaign records and [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Campaign records are now completed. Users can easily open the coupled [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] record directly from [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)].  
  
## Creating an Integration Table Mapping for Synchronizing Dynamics CRM Campaigns and Dynamics NAV Campaigns  
 For synchronization of data between [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] and [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] to work, mappings must exist to associate the table ID and fields of the integration table \(in this case table **50001 CRM Campaign**\) with the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] business data table \(in this case table **5081 Campaign**\). To accomplish this, you must create to types of mappings: *integration table mapping* and *integration field mapping*.  
  
-   An integration table mapping links the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] business data table to the integration table for the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity.  
  
-   A field mapping associates a field in a [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entity record with a field in a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] record. It basically determines which field in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] corresponds to which field in [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)]. You will typically have multiple field mappings for an entity.  
  
 You can create the integration table mapping directly in table **5335 Integration Table Mapping** and integration field mappings directly in table **5336 Integration Field Mappings** or you can add the mappings by modifying codeunit **5334 CRM Setup Defaults**. For a repeatable solution, we recommend that you integrate your changes in codeunit **5334 CRM Setup Defaults**.  
  
#### To create an Integration Table Mapping  
  
-   To create an integration table mapping directly in the table **5335 Integration Table Mapping**, follow these steps:  
  
    1.  Open the integration table **50001 CRM Campaign** in Table Designer, and then make a note the field numbers of the **CampaignId** and **ModifiedOn** fields. You will use these numbers later in this procedure.  
  
    2.  From Object Designer in the [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)], run table **5335 Integration Table Mapping** to open it in the [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)].  
  
    3.  Add a new record and fill in the following fields:  
  
        |Field|Value|  
        |-----------|-----------|  
        |Name|CAMPAIGN|  
        |Table ID|5071|  
        |Integration Table ID|50001|  
        |Synch. Codeunit ID|5340 \(CRM Integration Table Synch.\)|  
        |Integration Table UID Fld. No.|\[The field number of the primary key field **CampaignId** in table **CRM Campaign**\)|  
        |Int. Tbl. Modified On Fld. No.|\[The field number of the **ModifiedOn** field in the integration table **CRM Campaign**\]|  
        |Direction|Bidirectional \(synchronizes from [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] to [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] and from [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] to [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)]\).|  
  
-   To add an integration table mapping in codeunit **5334 CRM Setup Defaults**, follow these steps:  
  
    1.  Open the codeunit in Codeunit Designer.  
  
    2.  Add a local function called **ResetCampaignMapping**.  
  
    3.  Add the following local variables:  
  
        |Name|DataType|SubType|  
        |----------|--------------|-------------|  
        |CRMCampaign|Record|CRM Campaign|  
        |Campaign|Record|Campaign|  
        |IntegrationTableMappingName|Code||  
  
    4.  Add the following code to the function:  
  
        ```  
        IntegrationTableMappingName := 'CAMPAIGN';  
  
        RemoveIntegrationTableMapping(IntegrationTableMappingName);  
  
        InsertIntegrationTableMapping(  
          IntegrationTableMappingName,  
          DATABASE::"Campaign",  
          DATABASE::"CRM Campaign",  
          CODEUNIT::"CRM Integration Table Synch.",  
          CRMCampaign.FIELDNO(CampaignId),  
          CRMCampaign.FIELDNO(ModifiedOn),  
          '','',IntegrationTableMapping.Direction::FromIntegrationTable,TRUE);  
  
        ```  
  
 For each integration table mapping entry, there must be integration field mapping entries to map the individual fields of the records in the business table and integration table. The next step is to add integration field mappings for each field in the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Campaign table that you want to map to the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Campaign entity.  
  
#### To create Integration Fields Mappings  
  
-   To create an integration field mapping directly in table **5336 Integration Field Mapping**, follow these steps:  
  
    1.  From Object Designer, run table **5336 Integration Field Mapping** to open it in the [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)].  
  
    2.  Add a new record and fill in the following fields:  
  
        |Field|Value|  
        |-----------|-----------|  
        |No.|\[An identification number for the field mapping entry, such as 1\]|  
        |Integration Table Map Name|CAMPAIGN|  
        |Field No.|\[Field number for the **Description** field of the table **Campaign**, for example **2**\]|  
        |Integration Table Field No.|\[Field number for the **Name** field of the integration table **CRM Campaign**, for example **3**\]|  
        |Direction|Bidirectional|  
  
    3.  Repeat these steps for each field that you want to map.  
  
        > [!TIP]  
        >  If a field in one of the tables does not have a corresponding field in the other table, you can use a constant value. For an example of this, see the **CONTACTS Integration Table Mapping**.  
  
-   To add an integration field mapping in codeunit **5334 CRM Setup Defaults**, follow these steps:  
  
    1.  Open the codeunit in Codeunit Designer.  
  
    2.  In the function **ResetCampaignMapping**, add the following code. As an example, this code maps the `Description` field in the **Campaign** table to the `Name` field in the **CRM Campaign** integration table.  
  
        ```  
        InsertIntegrationFieldMap(  
          IntegrationTableMapName,  
          Campaign.FIELDNO("Description"),  
          CRMCampaign.FIELDNO(Name),  
          IntegrationFieldMap.Direction::Bidrectional,  
          '',FALSE,FALSE);  
  
        ```  
  
         Repeat this step for all fields that you want to map.  
  
    3.  After you make the changes to the CRM Setup Defaults, you can update the mappings by running the **[!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Connection Setup** page and choosing **Use Default Synchronization Setup**.  
  
 The next step is to add an action on page **5086  Campaign Card** that lets users to manually synchronize data between coupled campaign records in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] and [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)].  
  
#### To add an action for manual synchronization  
  
1.  Open page **5086 Campaign Card** in Page Designer, and then open the Action Designer for the page.  
  
2.  In the **Dynamics CRM** action group, before the **Coupling** action group, add a new action that has the name **CRMSynchronizeNow** and the caption **Synchronize Now**.  
  
3.  In the C\/AL code for the action, add a global variable that has the name **CRMIntegrationManagement** and references codeunit **5330 CRM Integration Management**, and then add the following line of code:  
  
    ```  
    CRMIntegrationManagement.UpdateOneNow(RECORDID);  
    ```  
  
4.  Save and compile the page.  
  
 Users can now manually synchronize [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Campaign records with [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] Campaign entity records from the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] client.  
  
> [!TIP]  
>  If you want to learn how to schedule the synchronization by using a job queue entry, examine the code on the **RecreateJobQueueEntry** function in codeunit **5330 CRM Integration Management** and see how it is called by the integration code for other [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] entities in the codeunit.  
  
## Customizing Synchronization  
 When synchronizing data, some entities may require custom code to successfully synchronize data. Other entities might require the initialization of fields, the validation of relationships, or the transformation of data.  
  
 During the synchronization process, certain events are published and raised by codeunit **5335 Integration Table Synch.**. You can add code that subscribes to these events, which enables you to add custom logic at different stages of the synchronization process. The following table describes the events that are published by codeunit **5335 Integration Table Synch.**.  
  
|Event|Description|  
|-----------|-----------------|  
|OnFindUnCoupledDestinationRecord|Occurs when the process tries to synchronize an uncoupled record \(new record\). Use this event to implement custom resolution algorithms for automatic mapping between records. For example, you can use this event to automatically map records by fields. You can see an example in codeunit **5341 CRM Int. Table. Subscriber**, which includes the event subscriber function **CRMTransactionCurrencyFindUncoupledDestinationRecord**. The event is used to resolve [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] currency codes with ISO currency codes in [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)].|  
|OnBeforeApplyRecordTemplate|Occurs before applying configuration templates to new records, and can be used to implement algorithms for determining what configuration template to use.|  
|OnAfterApplyRecordTemplate|Occurs after configuration templates are applied to new records, and can be used to change data after configuration templates have been applied.|  
|OnBeforeTransferRecordFields|Occurs before transferring data in modified fields \(which are defined in the Integration Field Mapping table\) from the source table to the destination table. It can be used to validate the source or destination before the data is moved.|  
|OnAfterTransferRecordFields|Occurs after transferring modified field data \(which are defined in the Integration Field Mapping table\) from the source table to the destination table. It can be used to transfer additional data, validate lookups, and so on. Setting the **AdditionalFieldsWereModified** parameter will cause a destination record modification even if no fields were modified.|  
|OnBeforeInsertRecord|Occurs before inserting a new destination record, and can be used to initialize fields, such as primary keys.|  
|OnAfterInsertRecord|Occurs after new destination record is inserted, and can be used to perform post\-insert operations such as updating related data.|  
|OnBeforeModifyRecord|Occurs before modifying an existing destination record, and can be used to validate\/change data before modification.|  
|OnAfterModifyRecord|Occurs after an existing destination record is modified, and can be used to perform post\-modify operations such as updating related data.|  
  
 For the synchronization of campaigns, you will use an event to create a custom rule that sets the **Comment** field in a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] campaign to **TRUE** if the **Message** field in a [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] campaign has data. You do this by subscribing to the **OnAfterTransferRecordFields** event that is published by codeunit **5335 Integration Table Synch**.  
  
 For more general information about how to subscribe to events, see [Subscribing to Events](../dynamics-nav/Subscribing-to-Events.md).  
  
#### To subscribe to the Integration Table Synch. OnAfterTransferRecordFields event  
  
1.  In the [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)], create a new codeunit that has the ID **50001** and the name **Campaign Event Subscriptions**.  
  
2.  Add a new function that is called **UpdateCampaignOnAfterTransferRecordFields**.  
  
3.  Set the following function properties:  
  
    |Property|Value|  
    |--------------|-----------|  
    |[Event Property](../dynamics-nav/Event-Property.md)|Subscriber|  
    |[EventPublisherObject Property](../dynamics-nav/EventPublisherObject-Property.md)|Codeunit Int. Table. Synch. \(ID 5335\)|  
    |[EventFunction Property](../dynamics-nav/EventFunction-Property.md)|OnAfterTransferRecordFields|  
  
     When prompted about overwriting the functions signature, choose the **Yes** button.  
  
4.  Add the following local variables to the function:  
  
    |Name|DataType|SubType|  
    |----------|--------------|-------------|  
    |CRMCampaign|Record|CRM Campaign|  
    |Campaign|Record|Campaign|  
  
5.  Add the following code to function to exit if the event is not trigged during synchronization between the **Campaign** table and **CRM Campaign** table.  
  
    ```  
    IF IntegrationTableMapping.NAME <> ‘CAMPAIGN’ THEN  
      EXIT; // Synchronization is not on the CAMPAIGN mapping  
    IF SourceRecordRef.NUMBER <> DATABASE::”CRM Campaign” THEN  
      EXIT; // The synch. direction is not from CRM Campaign to Campaign  
  
    ```  
  
6.  Add the following code to implement the logic to determine whether the **Message** field has a value:  
  
    ```  
    SourceRecordRef.GETTABLE(CRMCampaign);  
    DestinationRecordRef.GETTABLE(Campaign);  
  
    IF (CRMCampaign.Message <> '') AND (NOT Campaign.Comment) THEN BEGIN  
      Campaign.Comment := TRUE;  
      AdditionalFieldsWereModified := TRUE;  
    END ELSE BEGIN  
      IF (CRMCampaign.Message = '') AND Campaign.Comment THEN BEGIN  
        Campaign.Comment := FALSE;  
        AdditionalFieldsWereModified := TRUE;  
      END;  
    END;  
  
    IF AdditionalFieldsWereModified THEN  
      DestinationRecordRef.SETTABLE(Campaign);  
  
    ```  
  
7.  Save and compile the codeunit.  
  
 When you choose **Synchronize Now** on the **Campaign** page, and then choose to synchronize from [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] to [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)], the **Comment** field should be updated to indicate whether the **Message** field in the [!INCLUDE[crm](../dynamics-nav/includes/crm_md.md)] campaign has a value.  
  
## See Also  
 [Customizing Dynamics CRM and Dynamics NAV Integration](../dynamics-nav/Customizing-Dynamics-CRM-and-Dynamics-NAV-Integration.md)   
 [Introduction to Dynamics CRM Integration Customization in Dynamics NAV](../dynamics-nav/Introduction-to-Dynamics-CRM-Integration-Customization-in-Dynamics-NAV.md)
