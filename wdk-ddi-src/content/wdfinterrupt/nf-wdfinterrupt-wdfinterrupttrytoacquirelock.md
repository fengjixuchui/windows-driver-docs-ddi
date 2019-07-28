---
UID: NF:wdfinterrupt.WdfInterruptTryToAcquireLock
title: WdfInterruptTryToAcquireLock function (wdfinterrupt.h)
description: The WdfInterruptTryToAcquireLock method attempts to acquire an interrupt object's passive lock.
old-location: wdf\wdfinterrupttrytoacquirelock.htm
tech.root: wdf
ms.assetid: 272165BE-3DF2-410C-B60A-31B48A3F3231
ms.date: 02/26/2018
ms.keywords: WdfInterruptTryToAcquireLock, WdfInterruptTryToAcquireLock method, kmdf.wdfinterrupttrytoacquirelock, wdf.wdfinterrupttrytoacquirelock, wdfinterrupt/WdfInterruptTryToAcquireLock
ms.topic: function
f1_keywords:
 - "wdfinterrupt/WdfInterruptTryToAcquireLock"
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfInterruptTryToAcquireLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptTryToAcquireLock function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

 The <b>WdfInterruptTryToAcquireLock</b> method attempts to acquire an interrupt object's passive lock. 


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns



<b>WdfInterruptTryToAcquireLock</b> returns TRUE if it successfully acquires the interrupt’s lock. Otherwise, the method returns FALSE.




## -remarks



Drivers that use <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a> call <b>WdfInterruptTryToAcquireLock</b> to start a code sequence that executes at IRQL = PASSIVE_LEVEL while holding the passive-level interrupt lock that the driver configured in the interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure.

<b>WdfInterruptTryToAcquireLock</b> attempts to acquire the lock and then returns immediately, whether it has acquired the lock or not. If <b>WdfInterruptTryToAcquireLock</b> does successfully acquire the lock, the framework calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a> before returning so that normal kernel APCs are disabled.

For passive-level interrupt objects, drivers must call <b>WdfInterruptTryToAcquireLock</b> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>, when running in an arbitrary thread, such as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/">queue object callback function</a>. For example, the driver might call <b>WdfInterruptTryToAcquireLock</b> from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a>.  Doing so avoids the possibility of deadlock, as described in the Remarks section of <b>WdfInterruptAcquireLock</b>.

When running in  a non-arbitrary thread, such as a work item, the driver should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>.

When the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>, the framework releases the interrupt lock.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a> callback function, running in an arbitrary context, might call <b>WdfInterruptTryToAcquireLock</b> before performing interrupt-related work. If  the method returns FALSE, the driver queues a work item to perform the work in a non-arbitrary thread. The driver also supplies an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function that calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a> before it performs the work.

 In this example, the driver has specified <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">sequential</a> dispatching for the queue.   If the driver specified <i>any other dispatching method</i> for the queue, the driver should use an additional manual queue to retain requests for processing in the work item.  Code comments describe where to add such support.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
VOID EvtIoRead(
  __in  WDFQUEUE Queue,
  __in  WDFREQUEST Request,
  __in  size_t Length
    )
{
    DEVICE_CONTEXT    devCtx;
    devCtx = GetDeviceContext(WdfIoQueueGetDevice(Queue));
    
    //
    // Do any pre-acquiring interrupt lock work here.
    //
   

    //
    // Check if we can acquire the lock.
    //
    if (WdfInterruptTryToAcquireLock(devCtx->InterruptObject) {
        ReadFunctionLocked(Request);
        WdfInterruptReleaseLock(devCtx->InterruptObject);
        //
        // Do any post-releasing interrupt lock work here.
        // For example: complete the request, and so on.
        //
        ReadFunctionFinish(Request); 
    }
    else {
        WORK_ITEM_CONTEXT ctx;

        ctx = GetWorkItemContext(ReadWorkItem);
        ctx->Request = Request;

        // If previous queue is non-sequential, call WdfRequestForwardToIoQueue 
        // to store request in an additional manual queue.

        WdfWorkItemEnqueue(ReadWorkItem);
    }
}


VOID
EvtReadWorkItemCallback(
    WDFWORKITEM WorkItem
    )
{
    WORK_ITEM_CONTEXT wiCtx;
    DEVICE_CONTEXT    devCtx;

    wiCtx = GetWorkItemContext(ReadWorkItem);
    devCtx = GetDeviceContext(WdfWorkItemGetParentObject(WorkItem));

    // If delivery queue is non-sequential, call WdfIoQueueRetrieveNextRequest 
    // to retrieve request that we stored in EvtIoRead.

    //
    // Acquire interrupt lock.
    //
    WdfInterruptAcquireLock(devCtx->InterruptObject);
    ReadFunctionLocked(wiCtx->Request);
    WdfInterruptReleaseLock(devCtx->InterruptObject);

    //
    // Do any post-releasing interrupt lock work here.
    // For example: complete the request, and so on.
    //
    ReadFunctionFinish(wiCtx->Request); 
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/kmdf-wdfioqueueretrievenextrequest">WdfIoQueueRetrieveNextRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestrequeue">WdfRequestRequeue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551168">WdfWaitLockAcquire</a>
 

 

