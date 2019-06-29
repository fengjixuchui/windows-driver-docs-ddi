---
UID: NC:wdfdevice.EVT_WDF_DEVICE_D0_EXIT
title: EVT_WDF_DEVICE_D0_EXIT (wdfdevice.h)
description: A driver's EvtDeviceD0Exit event callback function performs operations that are needed when the driver's device leaves the D0 power state.
old-location: wdf\evtdeviced0exit.htm
tech.root: wdf
ms.assetid: bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_f2327720-a8e1-4e92-acb2-72378c3c5fb1.xml, EVT_WDF_DEVICE_D0_EXIT, EVT_WDF_DEVICE_D0_EXIT callback, EvtDeviceD0Exit, EvtDeviceD0Exit callback function, kmdf.evtdeviced0exit, wdf.evtdeviced0exit, wdfdevice/EvtDeviceD0Exit
ms.topic: callback
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
- EvtDeviceD0Exit
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_D0_EXIT callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceD0Exit</i> event callback function performs operations that are needed when the driver's device leaves the D0 power state.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param TargetState [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the device power state that the device is about to enter.


## -returns



If the <i>EvtDeviceD0Exit</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.




## -remarks



To register an <i>EvtDeviceD0Exit</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceD0Exit</i> callback function, the framework calls the function each time one of the driver's devices leaves its working (D0) state. A device leaves the D0 state when one of the following occurs:

<ul>
<li>
The system and all of its devices are about to leave their working states and enter a low-power state.

</li>
<li>
The device is about to enter a low-power state because it is idle, if the device supports low-power idle.

</li>
<li>
The Plug and Play manager is attempting to redistribute the system's hardware resources.

</li>
<li>
A user has indicated, typically by means of an application's user interface, that he or she wants to remove the device.

</li>
</ul>
The framework also calls the <i>EvtDeviceD0Exit</i> callback function after a device has been removed unexpectedly (surprise-removed).

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

Unless the device has been surprise-removed, the framework calls this callback function immediately after it disables the device's interrupts, but before the device's power is reduced from D0. The <i>TargetState</i> parameter identifies the device power state that the device is about to enter. 

The <i>EvtDeviceD0Exit</i> callback function must perform any operations that are necessary before the device enters the specified low-power state, such as saving any information that the driver will need later to restore the device to its D0 power state.

If the <i>TargetState</i> parameter is <b>WdfPowerDevicePrepareForHibernation</b>, the driver must not shut off the device, because the system will use the device when saving its hibernation file. 

If <i>TargetState</i> is <b>WdfPowerDeviceD3Final</b>, you should assume that the system is being turned off, the device is about to be removed, or a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/the-pnp-manager-redistributes-system-resources">resource rebalance</a> is in progress. If your driver must save information, it should write it to disk or some other permanent storage medium. 

For more information about drivers that provide this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-pnp-and-power-management-in-function-drivers">Supporting PnP and Power Management in Function Drivers</a>.


#### Examples

To define an <i>EvtDeviceD0Exit</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceD0Exit</i> callback function that is named <i>MyDeviceD0Exit</i>, use the <b>EVT_WDF_DEVICE_D0_EXIT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_D0_EXIT  MyDeviceD0Exit;</pre>
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
 MyDeviceD0Exit (
    WDFDEVICE  Device,
    WDF_POWER_DEVICE_STATE  TargetState
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_D0_EXIT</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_D0_EXIT</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a>
 

 

