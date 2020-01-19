---
UID: NF:wdfrequest.WdfRequestSend
title: WdfRequestSend function (wdfrequest.h)
description: The WdfRequestSend method sends a specified I/O request to a specified I/O target.
old-location: wdf\wdfrequestsend.htm
tech.root: wdf
ms.assetid: a0f4d4a4-f636-44df-911f-e3a615144fa9
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_3104cf0d-01d0-4299-a123-ba7a8cc0ada9.xml, WdfRequestSend, WdfRequestSend method, kmdf.wdfrequestsend, wdf.wdfrequestsend, wdfrequest/WdfRequestSend
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestSend"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, ReqCompletionRoutine, ReqMarkCancelableSend, ReqSendFail, ReqSendWhileSpinlock, RequestCompleted, RequestCompletedLocal, RequestFormattedValid, RequestGetStatusValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2, SyncReqSend2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: See Remarks section.
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
- WdfRequestSend
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestSend function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestSend</b> method sends a specified I/O request to a specified I/O target.


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param Target [in]

A handle to a framework I/O target object. For more information about how to obtain this handle, see the following Remarks section. 


### -param Options

<p>A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options"><b>WDF_REQUEST_SEND_OPTIONS</b></a> structure that contains caller-supplied request options. This parameter is optional and can be <b>NULL</b> if you do not want to enable any request options.</p>




## -returns



<b>WdfRequestSend</b> returns <b>TRUE</b> if the request was sent to the target. Otherwise, this method returns <b>FALSE</b>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The request object that the driver specifies for the <i>Request</i> parameter can be one that it <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/receiving-i-o-requests">received</a> or one that it created by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a> method.

To obtain a handle to an I/O target object, the driver can do one of the following:

<ul>
<li>
If the driver is using general I/O targets, it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/initializing-a-general-i-o-target">Initializing a General I/O Target</a>.

</li>
<li>
If the driver is using a specialized I/O target, it calls one or more methods that the specialized target object defines. For example, a driver for a USB device can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetiotarget">WdfUsbTargetDeviceGetIoTarget</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipegetiotarget">WdfUsbTargetPipeGetIoTarget</a>.

</li>
</ul>
By default, <b>WdfRequestSend</b> delivers the request to the target asynchronously, which means it returns immediately without waiting for the request to be completed. Optionally, the request can be delivered synchronously, which means <b>WdfRequestSend</b> does not return until a driver completes the request. To send the request synchronously, the driver must set the <b>WDF_REQUEST_SEND_OPTION_SYNCHRONOUS</b> flag in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.

If <b>WdfRequestSend</b> fails, or if your driver sets the WDF_REQUEST_SEND_OPTION_SYNCHRONOUS flag, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetstatus">WdfRequestGetStatus</a> immediately after calling <b>WdfRequestSend</b>.

If <b>WdfRequestSend</b> succeeds and your driver does not set the WDF_REQUEST_SEND_OPTION_SYNCHRONOUS flag, the driver typically calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetstatus">WdfRequestGetStatus</a> from within a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function.

If the driver sends the request synchronously, we recommend that the driver set a time-out value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure and the time-out flag in the <b>Flags</b> member of this structure.

If the driver supplies a time-out value, it should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestallocatetimer">WdfRequestAllocateTimer</a> before calling <b>WdfRequestSend</b>. This ensures that <b>WdfRequestSend</b> will not fail if there are insufficient system resources to allocate a timer.

 If the driver sets the <b>WDF_REQUEST_SEND_OPTION_SYNCHRONOUS</b> flag, it must call <b>WdfRequestSend</b> at IRQL = PASSIVE_LEVEL. If this flag is not set, the driver must call this method  at IRQL <= DISPATCH_LEVEL.
          <b>WdfRequestSend</b> sends the request at the caller's IRQL.

A driver cannot call <b>WdfRequestSend</b> to send an I/O request to a USB pipe, if the driver has configured a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">continuous reader</a> for the pipe.

When sending a request to a UMDF driver, a kernel-mode driver must follow the IRQL restrictions outlined in <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-drivers">Supporting Kernel-Mode Clients in UMDF Drivers</a>.

For more information about <b>WdfRequestSend</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.


#### Examples

The following code example is a shortened version of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a> callback function from the <a href="https://go.microsoft.com/fwlink/p/?linkid=256131">kmdf_fx2</a> sample driver. The function validates the request's buffer length, obtains a handle to the buffer, formats the request for a USB target, and sends the request.

```cpp
VOID 
OsrFxEvtIoWrite(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
    WDFUSBPIPE  pipe;
    NTSTATUS  status;
    WDFMEMORY  reqMemory;
    PDEVICE_CONTEXT  pDeviceContext;

    UNREFERENCED_PARAMETER(Queue);
    //
    // Check if the transfer size is valid.
    //
    if (Length > MAX_TRANSFER_BUFFER_SIZE) {
        status = STATUS_INVALID_PARAMETER;
        goto Exit;
    }
    //
    // Get driver-defined context space from
    // the device object. The driver stored the
    // pipe handle there.
    //
    pDeviceContext = GetDeviceContext(WdfIoQueueGetDevice(Queue));
    pipe = pDeviceContext->BulkWritePipe;
 
    //
    // Get a handle to a memory object that represents
    // the input buffer.
    //
    status = WdfRequestRetrieveInputMemory(Request, &reqMemory);
    if (!NT_SUCCESS(status)){
        goto Exit;
    }
    //
    // Format the request so it can be sent to a USB target.
    //
    status = WdfUsbTargetPipeFormatRequestForWrite(
                            pipe,
                            Request,
                            reqMemory,
                            NULL // Offsets
                            ); 
    if (!NT_SUCCESS(status)) {
        goto Exit;
    }
    //
    // Set a CompletionRoutine callback function.
    //
    WdfRequestSetCompletionRoutine(
                            Request,
                            EvtRequestReadCompletionRoutine,
                            pipe
                            );
    //
    // Send the request. If an error occurs, complete the request.
    //
    if (WdfRequestSend(
                       Request,
                       WdfUsbTargetPipeGetIoTarget(pipe),
                       WDF_NO_SEND_OPTIONS
                       ) == FALSE) {
        status = WdfRequestGetStatus(Request);
        goto Exit;
    }
Exit:
    if (!NT_SUCCESS(status)) {
        WdfRequestCompleteWithInformation(
                                          Request,
                                          status,
                                          0
                                          );
    }
    return;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestallocatetimer">WdfRequestAllocateTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetstatus">WdfRequestGetStatus</a>
 

 

