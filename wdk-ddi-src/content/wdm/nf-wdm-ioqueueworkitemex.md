---
UID: NF:wdm.IoQueueWorkItemEx
title: IoQueueWorkItemEx function (wdm.h)
description: The IoQueueWorkItemEx routine associates a WorkItemEx routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.
old-location: kernel\ioqueueworkitemex.htm
tech.root: kernel
ms.assetid: 277a6e13-dc2d-4170-a141-9df5b93eb504
ms.date: 04/30/2018
keywords: ["IoQueueWorkItemEx function"]
ms.keywords: IoQueueWorkItemEx, IoQueueWorkItemEx routine [Kernel-Mode Driver Architecture], k104_e14fae9d-5b8c-4683-8226-8694de253b64.xml, kernel.ioqueueworkitemex, wdm/IoQueueWorkItemEx
f1_keywords:
 - "wdm/IoQueueWorkItemEx"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoQueueWorkItemEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoQueueWorkItemEx function


## -description


The <b>IoQueueWorkItemEx</b> routine associates a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine_ex">WorkItemEx</a> routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.


## -parameters




### -param IoWorkItem [in]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure that was allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a> or initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem">IoInitializeWorkItem</a>. 


### -param WorkerRoutine [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine_ex">WorkItemEx</a> routine. 


### -param QueueType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_work_queue_type">WORK_QUEUE_TYPE</a> value that stipulates the type of system worker thread to handle the work item. Drivers must specify <b>DelayedWorkQueue</b>.


### -param Context [in, optional]

Specifies driver-specific information for the work item. The system passes this value as the <i>Context</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine_ex">WorkItemEx</a>.


## -remarks

The **IoQueueWorkItemEx** routine differs from [**IoQueueWorkItem**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem) in that the **WorkerRoutine** parameter is a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine_ex">WorkItemEx</a> callback routine, which provides the driver with a pointer to the [**IO_WORKITEM**](https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess) structure for the work item.

For more information about work items, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-worker-threads">System Worker Threads</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem">IoInitializeWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine_ex">WorkItemEx</a>
 

 

