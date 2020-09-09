---
UID: NF:wdfio.WdfIoQueueAssignForwardProgressPolicy
title: WdfIoQueueAssignForwardProgressPolicy function (wdfio.h)
description: The WdfIoQueueAssignForwardProgressPolicy method enables the framework's ability to guarantee forward progress for a specified I/O queue.
old-location: wdf\wdfioqueueassignforwardprogresspolicy.htm
tech.root: wdf
ms.assetid: 9512ecf2-ca59-4df8-bb60-c644444bc6fa
ms.date: 02/26/2018
keywords: ["WdfIoQueueAssignForwardProgressPolicy function"]
ms.keywords: DFQueueObjectRef_cd40c10b-367c-403a-8002-39662120f697.xml, WdfIoQueueAssignForwardProgressPolicy, WdfIoQueueAssignForwardProgressPolicy method, kmdf.wdfioqueueassignforwardprogresspolicy, wdf.wdfioqueueassignforwardprogresspolicy, wdfio/WdfIoQueueAssignForwardProgressPolicy
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoQueueAssignForwardProgressPolicy
 - wdfio/WdfIoQueueAssignForwardProgressPolicy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfIoQueueAssignForwardProgressPolicy
---

# WdfIoQueueAssignForwardProgressPolicy function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoQueueAssignForwardProgressPolicy</b> method enables the framework's ability to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">guarantee forward progress</a> for a specified I/O queue.

## -parameters

### -param Queue 

[in]
A handle to a framework queue object.

### -param ForwardProgressPolicy 

[in]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_forward_progress_policy">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.

## -returns

<b>WdfIoQueueAssignForwardProgressPolicy</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of these values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure is incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The amount of available memory is too low.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>. In addition, if your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request">EvtIoAllocateResourcesForReservedRequest</a> callback function returns an error status value, <b>WdfIoQueueAssignForwardProgressPolicy</b> returns that value.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

The<b>WdfIoQueueAssignForwardProgressPolicy</b> method creates request objects that the framework reserves for low-memory situations and registers callback functions that the framework calls to handle low-memory situations.

In KMDF version 1.9, the I/O queue that the <i>Queue</i> parameter represents must be a device's default I/O queue, or a queue for which your driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurerequestdispatching">WdfDeviceConfigureRequestDispatching</a>. The driver can call <b>WdfIoQueueAssignForwardProgressPolicy</b> any time after it has called <b>WdfDeviceConfigureRequestDispatching</b>.

In KMDF versions 1.11 and later,  the I/O queue that the <i>Queue</i> parameter represents can be any queue that receives a request directly from the framework. For example, the driver might specify a queue to which it will <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">dynamically forward IRPs</a>.

Before <b>WdfIoQueueAssignForwardProgressPolicy</b> returns, the framework does the following:

<ul>
<li>
Creates and stores the number of request objects that the driver has specified for the <b>TotalForwardProgressRequests</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_forward_progress_policy">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.

</li>
<li>
If the driver previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a>, each allocation includes context space that <b>WdfDeviceInitSetRequestAttributes</b> specified. 

</li>
<li>
Calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request">EvtIoAllocateResourcesForReservedRequest</a> callback function for each request object that the framework creates.

</li>
</ul>
After the driver has called <b>WdfIoQueueAssignForwardProgressPolicy</b> to create reserved request objects, the framework uses those reserved objects whenever its attempt to create a new request object fails. (Typically, such failures are caused by low memory situations.) 

The framework deletes its reserved request objects only when it deletes the framework queue object that they belong to. If your driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a> and specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function for its request objects, the framework calls these callback functions for its reserved request objects when it deletes the objects.

For more information about the <b>WdfIoQueueAssignForwardProgressPolicy</b> method and how to use the framework's guaranteed forward progress capability, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.


#### Examples

This code example configures a previously created I/O queue to receive write requests, and then it enables guaranteed forward progress for the queue.

```cpp
#define MAX_RESERVED_REQUESTS 10

WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY queueForwardProgressPolicy;
WDFQUEUE writeQueue;
NTSTATUS status = STATUS_SUCCESS;
...
status = WdfDeviceConfigureRequestDispatching(
             device,
             writeQueue,
             WdfRequestTypeWrite
             );
if(!NT_SUCCESS(status)) {
    return status;
}
WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_DEFAULT_INIT(
    &queueForwardProgressPolicy,
    MAX_RESERVED_REQUESTS
    );
status = WdfIoQueueAssignForwardProgressPolicy(
             writeQueue,
             &queueForwardProgressPolicy
             );
if(!NT_SUCCESS(status)) {
    return status;
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request">EvtIoAllocateResourcesForReservedRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_forward_progress_policy">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurerequestdispatching">WdfDeviceConfigureRequestDispatching</a>

