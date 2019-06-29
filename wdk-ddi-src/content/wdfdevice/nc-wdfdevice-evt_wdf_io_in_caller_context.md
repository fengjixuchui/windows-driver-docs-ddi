---
UID: NC:wdfdevice.EVT_WDF_IO_IN_CALLER_CONTEXT
title: EVT_WDF_IO_IN_CALLER_CONTEXT (wdfdevice.h)
description: A driver's EvtIoInCallerContext event callback function preprocesses an I/O request before the framework places it into an I/O queue.
old-location: wdf\evtioincallercontext.htm
tech.root: wdf
ms.assetid: b8bcea29-e404-490e-9d0c-02c96a5690ab
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_027a6221-e735-4a5c-a378-d9d9236f21ae.xml, EVT_WDF_IO_IN_CALLER_CONTEXT, EVT_WDF_IO_IN_CALLER_CONTEXT callback, EvtIoInCallerContext, EvtIoInCallerContext callback function, kmdf.evtioincallercontext, wdf.evtioincallercontext, wdfdevice/EvtIoInCallerContext
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtIoInCallerContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_IN_CALLER_CONTEXT callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtIoInCallerContext</i> event callback function preprocesses an I/O request before the framework places it into an I/O queue.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Request [in]

A handle to a framework request object.


## -returns



None




## -remarks



The framework calls a driver's <i>EvtIoInCallerContext</i> callback function so that the driver can examine each I/O request, and possibly perform preliminary processing on the request, before the framework places it in an I/O queue. To register an <i>EvtIoInCallerContext</i> callback function for a device, the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetioincallercontextcallback">WdfDeviceInitSetIoInCallerContextCallback</a>. 

If a driver registers an <i>EvtIoInCallerContext</i> callback function for a device, the framework calls the callback function each time it receives an I/O request for the device. The callback function is called in the thread context of the process that sent the I/O request to the driver. This process is either the next-higher level driver or, if the driver is at the top of the driver stack, a user-mode application. 

This callback function's primary purpose is to enable framework-based drivers to support the buffer-access method that is called <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">neither buffered nor direct I/O</a>. For this buffer-access method, the driver must access received buffers in the originator's process context.

After the callback function has obtained a request's buffers, it can store buffer addresses or handles in the request object's context storage. (The driver sets the size of the request object's context storage area by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a>.)

Because the request does not yet belong to an I/O queue, the framework does not lock or synchronize the request. The driver is responsible for any synchronization that might be necessary. For more information about synchronization, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.

After the callback function has finished preprocessing the request, it must either queue it by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceenqueuerequest">WdfDeviceEnqueueRequest</a> or complete it by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> (if an error is detected).

For more information about the <i>EvtIoInCallerContext</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Intercepting an I/O Request before it is Queued</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

If a driver has configured an I/O queue to support <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">guaranteed forward progress</a>, the framework might not call the driver's <i>EvtIoInCallerContext</i> callback function during low-memory situations. If all of the framework's reserved request objects are in use, the framework postpones processing the I/O request until a reserved request object is available. In this situation, the framework cannot call the <i>EvtIoInCallerContext</i> callback function for the postponed I/O request because, when a reserved request object becomes available, the framework will no longer be running in the thread context of the process that sent the I/O request to the driver.

The <i>EvtIoInCallerContext</i> callback function is called at the IRQL of the calling thread. If the calling thread is from a user-mode application, the callback function is called at IRQL = PASSIVE_LEVEL. If the calling thread is from a higher-level kernel-mode driver, your driver's <i>EvtIoInCallerContext</i> callback function can be called at IRQL <= DISPATCH_LEVEL if both the callback function and the higher-level driver are designed to pass the request at IRQL <= DISPATCH_LEVEL.


#### Examples

To define an <i>EvtIoInCallerContext</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoInCallerContext</i> callback function that is named <i>MyIoInCallerContext</i>, use the <b>EVT_WDF_IO_IN_CALLER_CONTEXT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_IN_CALLER_CONTEXT  MyIoInCallerContext;</pre>
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
 MyIoInCallerContext  (
    WDFDEVICE  Device,
    WDFREQUEST  Request
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_IN_CALLER_CONTEXT</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_IN_CALLER_CONTEXT</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a>
 

 

