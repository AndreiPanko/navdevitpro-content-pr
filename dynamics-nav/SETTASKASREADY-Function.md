---
title: "SETTASKASREADY Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 90204123-a179-409d-921e-fc65f240596d
caps.latest.revision: 3
manager: edupont
---
# SETTASKASREADY Function
Sets a task that runs a codeunit to the ready state. The task will not run unless it is in the ready state.  
  
## Syntax  
  
```  
[OK =: ]SETTASKASREADY(Task[,NotBefore])  
```  
  
#### Parameters  
 *Task*  
 Type: GUID  
  
 The unique identifier of the task. The unique identifier is returned by the CREATETASK function.  
  
 *NotBefore*  
 Type: DateTime  
  
 Specifies the date and time that you want to make the task ready.  
  
 *RecordID*  
 Type: RecordID  
  
 Specifies the recordID of the record that you want to run the task on.  
  
## Property Value\/Return Value  
 Type: Boolean  
  
 **true** if a task has been set to ready; otherwise, **false**.  
  
## Remarks  
 For more information about tasks and **TASKSCEDULER** data type functions, see managing tasks [Task Scheduler](../dynamics-nav/Task-Scheduler.md).  
  
## Example  
 The following example creates a task, and then uses the SETTASKASREADY function to set the task to ready.  
  
 The code requires that you create the following C\/AL variable.  
  
|Variable|DataType|  
|--------------|--------------|  
|TaskID|GUID|  
  
```  
TaskID := TASKSCHEDULER.CREATETASK(CODEUNIT::"Job Queue Dispatcher", CODEUNIT::"Job Queue Error Handler");  
TASKSCHEDULER.SETTASKASREADY(taskID);  
```  
  
## See Also  
 [TaskScheduler Data Type](../dynamics-nav/TaskScheduler-Data-Type.md)   
 [CREATETASK Function](../dynamics-nav/CREATETASK-Function.md)   
 [CANCELTASK Function](../dynamics-nav/CANCELTASK-Function.md)   
 [TASKEXISTS Function](../dynamics-nav/TASKEXISTS-Function.md)