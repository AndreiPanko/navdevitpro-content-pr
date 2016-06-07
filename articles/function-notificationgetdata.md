<properties
                pageTitle="GETDATA Function (Notification) | Project “Madeira”"
                description="Describes the GETDATA function of the Notification data type for sending notifications"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# GETDATA Function (Notification)
Retrieves data that was passed to a notification instance as specified by a [SETDATA function](function-notificationsetdata.md) call.

```
Value := GETDATA(Name)
```

## Parameters
*Name*

Type: Type: Code or text

The name of the data item that is specified by the SETDATA function call.

## Remarks
You use the SETDATA and GETDATA functions for transferring data in a notification. The functions are typically needed for handling actions on the notification. The SETDATA function is called from the source of the notification, while the GETDATA function is called from the action code.

For more information and a detailed example, see [Notifications](notifications-developing.md).

##  Example
The following code sets the data for a notification:
```
MyNotification.MESSAGE := 'This is a notification';
MyNotification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
MyNotification.SETDATA('Created',FORMAT(CURRENTDATETIME,0,9));
MyNotification.SETDATA('ID',FORMAT(CREATEGUID,0,9));
MyNotification.ADDACTION('Action 1',CODEUNIT::"Action Handler",'RunAction1');
MyNotification.ADDACTION('Action 2',CODEUNIT::"Action Handler",'RunAction2');
MyNotification.SEND;
```
The following code gets the data for a notification:

```
MyNotification.GETDATA('Created');
MyNotification.GETDATA('ID');
```

## See Also  
[SCOPE Function(Notification)](function-notificationscope.md)  
[SEND Function (Notification)](function-notificationsend.md)  
[Notifications](notifications-developing.md)
