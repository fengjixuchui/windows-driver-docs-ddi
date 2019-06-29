---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL
title: EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL (wdfio.h)
description: A driver's EvtIoDeviceControl event callback function processes a specified device I/O control request.
old-location: wdf\evtiodevicecontrol.htm
tech.root: wdf
ms.assetid: 3e3c4c53-e557-4bd1-8b7d-be59dde4b9ce
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_90eafb20-dd9c-49ca-b435-fdee9b13e4e1.xml, EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL, EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL callback, EvtIoDeviceControl, EvtIoDeviceControl callback function, kmdf.evtiodevicecontrol, wdf.evtiodevicecontrol, wdfio/EvtIoDeviceControl
ms.topic: callback
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfio.h
api_name:
- EvtIoDeviceControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoDeviceControl</i> event callback function processes a specified device I/O control request.


## -parameters




### -param Queue [in]

A handle to the framework queue object that is associated with the I/O request.


### -param Request [in]

A handle to a framework request object.


### -param OutputBufferLength [in]

The length, in bytes, of the request's output buffer, if an output buffer is available.


### -param InputBufferLength [in]

The length, in bytes, of the request's input buffer, if an input buffer is available.


### -param IoControlCode [in]

The driver-defined or system-defined I/O control code (IOCTL) that is associated with the request.


## -returns



None




## -remarks



A driver registers an <i>EvtIoDeviceControl</i> callback function when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoDeviceControl</i> callback function for a device's I/O queue, the callback function receives every I/O control request (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>) from the queue. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>.

The <i>EvtIoDeviceControl</i> callback function must process each received I/O request in some manner. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/processing-i-o-requests">Processing I/O Requests</a>.

Drivers receive I/O control requests when a user application calls <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> (described in Microsoft Windows SDK documentation) or when another driver creates a request by calling either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetformatrequestforioctl">WdfIoTargetFormatRequestForIoctl</a>.

The type of operation to be performed depends on the value of the <i>IoControlCode</i> parameter. You must determine the set of <i>IoControlCode</i> values that applications and other drivers can send to your driver. For more information about IOCTLs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-i-o-control-codes">Using I/O Control Codes</a>.

Most device I/O control operations require an input buffer, an output buffer, or both. For information about how the driver can access a request's buffers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

The techniques that your driver can use to access the request's input and output buffers (if they exist) depend on the <i>TransferType</i> field of the IOCTL. The value of the IOCTL's <i>TransferType</i> field can be METHOD_BUFFERED, METHOD_DIRECT_IN, METHOD_DIRECT_OUT, or METHOD_NEITHER. For more information about the <i>TransferType</i> field, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/defining-i-o-control-codes">Defining I/O Control Codes</a>.

The <i>EvtIoDeviceControl</i> callback function can be called at IRQL <= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoDeviceControl</i> callback function should not call the following queue object methods:<dl>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuedrainsynchronously">WdfIoQueueDrainSynchronously</a>
</dd>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuepurgesynchronously">WdfIoQueuePurgeSynchronously</a>
</dd>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuestopsynchronously">WdfIoQueueStopSynchronously</a>
</dd>
</dl>



#### Examples

To define an <i>EvtIoDeviceControl</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoDeviceControl</i> callback function that is named <i>MyIoDeviceControl</i>, use the <b>EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL  MyIoDeviceControl;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyIoDeviceControl (
 IN WDFQUEUE  Queue,
    WDFREQUEST  Request,
    size_t  OutputBufferLength,
    size_t  InputBufferLength,
    ULONG  IoControlCode
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_internal_device_control">EvtIoInternalDeviceControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetformatrequestforioctl">WdfIoTargetFormatRequestForIoctl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

