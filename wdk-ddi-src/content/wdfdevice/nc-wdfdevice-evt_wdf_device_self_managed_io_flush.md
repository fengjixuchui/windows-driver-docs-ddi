---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH (wdfdevice.h)
description: A driver's EvtDeviceSelfManagedIoFlush event callback function handles flush activity for the device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagedioflush.htm
tech.root: wdf
ms.assetid: ad4ace83-c6c1-4b5f-b998-f46f3e721165
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_d464c7ae-10fa-4838-b152-9bbaeaac76de.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH, EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH callback, EvtDeviceSelfManagedIoFlush, EvtDeviceSelfManagedIoFlush callback function, kmdf.evtdeviceselfmanagedioflush, wdf.evtdeviceselfmanagedioflush, wdfdevice/EvtDeviceSelfManagedIoFlush
ms.topic: callback
f1_keywords:
 - "wdfdevice/EvtDeviceSelfManagedIoFlush"
req.header: wdfdevice.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceSelfManagedIoFlush
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceSelfManagedIoFlush</i> event callback function handles flush activity for the device's self-managed I/O operations.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -remarks



To register an <i>EvtDeviceSelfManagedIoFlush</i> callback function, a driver must call  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoFlush</i> callback function, the framework calls it after the device has been removed. The driver should flush (that is, remove) I/O requests that are associated with the device's self-managed I/O operations.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-self-managed-i-o">Using Self-Managed I/O</a>.

You must declare the function by using the EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH type. For more information, see the following Example section.


#### Examples

To define an <i>EvtDeviceSelfManagedIoFlush</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceSelfManagedIoFlush</i> callback function that is named <i>MyDeviceSelfManagedIoFlush</i>, use the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH  MyDeviceSelfManagedIoFlush;</pre>
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
 MyDeviceSelfManagedIoFlush (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_FLUSH</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_restart">EvtDeviceSelfManagedIoRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a>
 

 

