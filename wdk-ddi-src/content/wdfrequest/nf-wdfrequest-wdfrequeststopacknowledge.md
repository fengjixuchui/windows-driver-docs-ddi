---
UID: NF:wdfrequest.WdfRequestStopAcknowledge
title: WdfRequestStopAcknowledge function (wdfrequest.h)
description: The WdfRequestStopAcknowledge method informs the framework that the driver has stopped processing a specified I/O request.
old-location: wdf\wdfrequeststopacknowledge.htm
tech.root: wdf
ms.assetid: 70f90cfd-9828-41a6-a7f9-6b0033e46b74
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_14594eba-ca7f-433b-9fd4-717053a09158.xml, WdfRequestStopAcknowledge, WdfRequestStopAcknowledge method, kmdf.wdfrequeststopacknowledge, wdf.wdfrequeststopacknowledge, wdfrequest/WdfRequestStopAcknowledge
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestStopAcknowledge"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, EvtIoStopCompleteOrStopAck, EvtIoStopResume, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal, StopAckWithinEvtIoStop
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
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
- WdfRequestStopAcknowledge
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestStopAcknowledge function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestStopAcknowledge</b> method informs the framework that the driver has stopped processing a specified I/O request.


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param Requeue [in]

A Boolean value that, if <b>TRUE</b>, causes the framework to requeue the request into the queue so that the framework will deliver it to the driver again. If <b>FALSE</b>, the framework does not requeue the request. For more information, see the following Remarks section.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




If a driver registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function for an I/O queue, the framework calls it when the queue's underlying device is leaving its working (D0) state. The framework calls the <i>EvtIoStop</i> callback function for every I/O request that the driver has not <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completed</a>, including requests that the driver <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-ownership">owns</a> and those that it has <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/forwarding-i-o-requests">forwarded</a> to an I/O target. The driver must complete, cancel, or postpone processing of each request by doing one of the following: 

<ul>
<li>
If the driver owns the request, it can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> to complete or cancel the request.

</li>
<li>
If the driver has forwarded the request to an I/O target, it can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcancelsentrequest">WdfRequestCancelSentRequest</a> to attempt to cancel the request.

</li>
<li>
If the driver postpones processing the request, it must call <b>WdfRequestStopAcknowledge</b>.

</li>
</ul>
If your driver calls <b>WdfRequestStopAcknowledge</b>, it must call this method from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function.

The framework does not allow the device to leave its working (D0) state until the driver has completed, canceled, or postponed every request that an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function receives.  Potentially, this inaction can prevent a system from entering its hibernation state or another low system power state.

When a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function calls <b>WdfRequestStopAcknowledge</b>, it can set the <i>Requeue</i> parameter to <b>TRUE</b> or <b>FALSE</b>: 

<ul>
<li>
Setting <i>Requeue</i> to <b>TRUE</b> causes the framework to place the request back into its I/O queue.

When the underlying device returns to its working (D0) state, the framework will redeliver the request to the driver. 

</li>
<li>
Setting <i>Requeue</i> to <b>FALSE</b> causes the framework not to requeue the request. If the driver <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-ownership">owns</a> the request, ownership remains with the driver. If the driver has forwarded the request, the driver is responsible for handling the request when it is completed. The driver must stop doing any I/O processing that requires hardware access. 

When the underlying device returns to its working (D0) state, the framework will call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_resume">EvtIoResume</a> callback function, so that the driver can continue processing the request.

</li>
</ul>
If the driver had previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> before calling <b>WdfRequestStopAcknowledge</b> with <i>Requeue</i> set to <b>TRUE</b>.

Before calling <b>WdfRequestStopAcknowledge</b>, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function must stop all processing of the I/O request that requires accessing the underlying device, because the device is about to enter a low-power state.

For more information about the <b>WdfRequestStopAcknowledge</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-power-managed-i-o-queues">Using Power-Managed I/O Queues</a>.


#### Examples

If a driver calls <b>WdfRequestStopAcknowledge</b> with <i>Requeue</i> set to <b>TRUE</b>, it must previously call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>.

The following code example is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function that checks to see if a received request is cancelable and, if it is, calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>. If <b>WdfRequestUnmarkCancelable</b> returns STATUS_CANCELLED, the example just returns because the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a> callback function will handle the request. Otherwise, the example calls <b>WdfRequestStopAcknowledge</b> and specifies <b>TRUE</b> so that the framework requeues the request when the underlying device returns to its working (D0) state.

```cpp
VOID
MyEvtIoStop(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN ULONG  ActionFlags
    )
{
    NTSTATUS status;

    // TODO: Take steps here to suspend and, if necessary, roll back any processing that has already occurred on this request

    if (ActionFlags & WdfRequestStopRequestCancelable) {
        status = WdfRequestUnmarkCancelable(Request);
        if (status == STATUS_CANCELLED) {
            return;
        }
    }

    // Inform framework that driver is postponing processing, cause framework to redeliver request when device returns to D0

    WdfRequestStopAcknowledge(Request, TRUE);
}
```
Typically, if a driver calls <b>WdfRequestStopAcknowledge</b> with <i>Requeue</i> set to <b>FALSE</b>, it leaves the request cancelable.

The following code example is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function that calls <b>WdfRequestStopAcknowledge</b> and specifies <b>FALSE</b> so that the framework eventually calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_resume">EvtIoResume</a> callback function, where the driver resumes processing of the request.

You might use code like this if it is acceptable to halt processing of a specific request and continue it later, rather than having the request redelivered and restarting processing from the beginning.

```cpp
VOID
MyEvtIoStop(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN ULONG  ActionFlags
    )
{

    //TODO: Take steps here to suspend processing of the request so it can be resumed when power returns
	 
    // Acknowledge the stop, but leave the request under driver's ownership.
    // Provide a corresponding EvtIoResume handler to resume processing when power returns

    WdfRequestStopAcknowledge(Request, FALSE);
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_cancel">EvtRequestCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>
 

 

