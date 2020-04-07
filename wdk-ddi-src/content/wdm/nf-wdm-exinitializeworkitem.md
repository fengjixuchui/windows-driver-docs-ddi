---
UID: NF:wdm.ExInitializeWorkItem
title: ExInitializeWorkItem function (wdm.h)
description: ExInitializeWorkItem initializes a work-queue item with a caller-supplied context and callback routine to be queued for execution when a system worker thread is given control.
old-location: ifsk\exinitializeworkitem.htm
tech.root: ifsk
ms.assetid: e26e7e68-0d0c-42fe-9342-ebbf2bb8f830
ms.date: 04/16/2018
keywords: ["ExInitializeWorkItem function"]
ms.keywords: ExInitializeWorkItem, ExInitializeWorkItem routine [Installable File System Drivers], exref_815c9796-c2e5-4362-926a-2fb509f3a1ae.xml, ifsk.exinitializeworkitem, wdm/ExInitializeWorkItem
f1_keywords:
 - "wdm/ExInitializeWorkItem"
req.header: wdm.h
req.include-header: FltKernel.h, Ntifs.h, Ntddk.h, Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- ExInitializeWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExInitializeWorkItem function


## -description


<b>ExInitializeWorkItem</b> initializes a work-queue item with a caller-supplied context and callback routine to be queued for execution when a system worker thread is given control. 
<div class="alert"><b>Note</b>  Use this routine with extreme caution. (See the following Remarks section.)</div><div> </div>

## -parameters




### -param Item [in]

Pointer to a caller-allocated WORK_QUEUE_ITEM structure to be initialized. This structure must be allocated from nonpaged pool. The callback routine specified in the <i>Routine</i> parameter is responsible for freeing this work item when it is no longer needed by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreepoolwithtag">ExFreePoolWithTag</a>. 


### -param Routine [in]

Pointer to a caller-defined routine that will be called to process the work item. This routine will be called in the context of a system thread at IRQL PASSIVE_LEVEL. This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PWORKER_THREAD_ROUTINE)(
    IN PVOID Parameter
    );</pre>
</td>
</tr>
</table></span></div>




#### Parameter

Context information pointer that was passed in the <i>Context</i> parameter. 


### -param Context [in]

Pointer to caller-supplied context information to be passed to the callback routine specified in the <i>Routine</i> parameter. 


## -remarks



<b>ExInitializeWorkItem</b> initializes the work item with the specified callback routine and context pointer and <b>NULL</b> list pointers. 

To add the work item to a system work queue, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exqueueworkitem">ExQueueWorkItem</a>. 

Work items are a limited resource, and drivers should only allocate them as needed. For example, do not allocate a work item in <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> for the driver's dedicated use. 

<b>ExInitializeWorkItem</b>
      and 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exqueueworkitem">ExQueueWorkItem</a>
      can only be used in cases where the specified work item is not associated with any device object or device stack. In all other cases, drivers should use 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>
     , 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeworkitem">IoFreeWorkItem</a>
     , and 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>, because only these routines ensure that the device object associated with the specified work item remains available until the work item has been processed. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreepoolwithtag">ExFreePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exqueueworkitem">ExQueueWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeworkitem">IoFreeWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_work_queue_item">WORK_QUEUE_ITEM</a>
 

 

