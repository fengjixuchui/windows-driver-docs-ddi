---
UID: NC:wdfdevice.EVT_WDF_DEVICE_QUERY_STOP
title: EVT_WDF_DEVICE_QUERY_STOP (wdfdevice.h)
description: A driver's EvtDeviceQueryStop event callback function determines whether a specified device can be stopped so that the PnP manager can redistribute system hardware resources.
old-location: wdf\evtdevicequerystop.htm
tech.root: wdf
ms.assetid: 4f2ed29a-fed0-4286-81db-7a4c8a15a7dd
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_QUERY_STOP callback function"]
ms.keywords: DFDeviceObjectGeneralRef_06abba34-8d71-46bf-8496-b6f27fe66dce.xml, EVT_WDF_DEVICE_QUERY_STOP, EVT_WDF_DEVICE_QUERY_STOP callback, EvtDeviceQueryStop, EvtDeviceQueryStop callback function, kmdf.evtdevicequerystop, wdf.evtdevicequerystop, wdfdevice/EvtDeviceQueryStop
f1_keywords:
 - "wdfdevice/EvtDeviceQueryStop"
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
- EvtDeviceQueryStop
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_QUERY_STOP callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceQueryStop</i> event callback function determines whether a specified device can be stopped so that the PnP manager can redistribute system hardware resources.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the driver determines that the device can be stopped, the <i>EvtDeviceQueryStop</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.




## -remarks



To register an <i>EvtDeviceQueryStop</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the device and driver support idle power-down, the device might not be in its working state when the framework calls the driver's <i>EvtDeviceQueryStop</i> callback function. The callback function can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicestopidle">WdfDeviceStopIdle</a> to force the device into its working (D0) state, and then the callback function can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceresumeidle">WdfDeviceResumeIdle</a> before it returns.

For more information about the <i>EvtDeviceQueryStop</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-requests-to-stop-a-device">Handling Requests to Stop a Device</a>.

The framework does not synchronize the <i>EvtDeviceQueryStop</i> callback function with other PnP and power management callback functions. For information about how the framework synchronizes the execution of a driver's event callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>. 


#### Examples

To define an <i>EvtDeviceQueryStop</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceQueryStop</i> callback function that is named <i>MyDeviceQueryStop</i>, use the <b>EVT_WDF_DEVICE_QUERY_STOP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_QUERY_STOP  MyDeviceQueryStop;</pre>
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
 MyDeviceQueryStop (
    WDFDEVICE  Device
    )
 {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_QUERY_STOP</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_QUERY_STOP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_query_remove">EvtDeviceQueryRemove</a>
 

 

