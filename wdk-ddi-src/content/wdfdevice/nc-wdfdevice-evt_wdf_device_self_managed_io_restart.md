---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART (wdfdevice.h)
description: A driver's EvtDeviceSelfManagedIoRestart event callback function restarts a device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagediorestart.htm
tech.root: wdf
ms.assetid: 13d7fbc6-6f93-4ef9-abd4-f2adc4e8e23a
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART callback function"]
ms.keywords: DFDeviceObjectGeneralRef_31761962-577a-4a53-8b55-226801f42960.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART, EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART callback, EvtDeviceSelfManagedIoRestart, EvtDeviceSelfManagedIoRestart callback function, kmdf.evtdeviceselfmanagediorestart, wdf.evtdeviceselfmanagediorestart, wdfdevice/EvtDeviceSelfManagedIoRestart
f1_keywords:
 - "wdfdevice/EvtDeviceSelfManagedIoRestart"
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceSelfManagedIoRestart
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceSelfManagedIoRestart</i> event callback function restarts a device's self-managed I/O operations.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the <i>EvtDeviceSelfManagedIoRestart</i> callback function encounters no errors, it must return STATUS_SUCCESS, or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. If NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework stops the device and unloads the device's drivers. 

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a> callback functions. 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.




## -remarks



To register an <i>EvtDeviceSelfManagedIoRestart</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoRestart</i> callback function, the framework calls it each time that the device returns from a low-power state to its working (D0) state. The framework calls the <i>EvtDeviceSelfManagedIoRestart</i> callback function only after calling the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a> callback function.

The driver's <i>EvtDeviceSelfManagedIoRestart</i> callback function must do whatever is needed to resume the device's self-managed I/O operations.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-self-managed-i-o">Using Self-Managed I/O</a>.

The <i>EvtDeviceSelfManagedIoRestart</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.


#### Examples

To define an <i>EvtDeviceSelfManagedIoRestart</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceSelfManagedIoRestart</i> callback function that is named <i>MyDeviceSelfManagedIoRestart</i>, use the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART  MyDeviceSelfManagedIoRestart;</pre>
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
NTSTATUS
 MyDeviceSelfManagedIoRestart (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_RESTART</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a>
 

 

