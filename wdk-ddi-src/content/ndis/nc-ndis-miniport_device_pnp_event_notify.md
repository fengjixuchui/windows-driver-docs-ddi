---
UID: NC:ndis.MINIPORT_DEVICE_PNP_EVENT_NOTIFY
title: MINIPORT_DEVICE_PNP_EVENT_NOTIFY (ndis.h)
description: NDIS calls a miniport driver's MiniportDevicePnPEventNotify function to notify the driver of Plug and Play (PnP) events.
old-location: netvista\miniportdevicepnpeventnotify.htm
tech.root: netvista
ms.assetid: e41240c0-17be-42ef-a72c-c5311115cf64
ms.date: 05/02/2018
keywords: ["MINIPORT_DEVICE_PNP_EVENT_NOTIFY callback function"]
ms.keywords: MINIPORT_DEVICE_PNP_EVENT_NOTIFY, MINIPORT_DEVICE_PNP_EVENT_NOTIFY callback, MiniportDevicePnPEventNotify, MiniportDevicePnPEventNotify callback function [Network Drivers Starting with Windows Vista], miniport_functions_ref_5f503cae-149c-447c-b3f5-cb09d2c47ad7.xml, ndis/MiniportDevicePnPEventNotify, netvista.miniportdevicepnpeventnotify
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: NdisOidComplete
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MINIPORT_DEVICE_PNP_EVENT_NOTIFY
 - ndis/MINIPORT_DEVICE_PNP_EVENT_NOTIFY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - MiniportDevicePnPEventNotify
---

# MINIPORT_DEVICE_PNP_EVENT_NOTIFY callback function


## -description

NDIS calls a miniport driver's 
   <i>MiniportDevicePnPEventNotify</i> function to notify the driver of Plug and Play
   (PnP) events.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_DEVICE_PNP_EVENT_NOTIFY</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportAdapterContext 

[in]
A handle to a context area that the miniport driver allocated in its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for an miniport adapter.

### -param NetDevicePnPEvent 

[in]
A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_device_pnp_event">NET_DEVICE_PNP_EVENT</a> structure that
     describes a device Plug and Play event.

## -remarks

A driver specifies the 
    <i>MiniportDevicePnPEventNotify</i> entry point when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function.

NDIS calls the driver's 
    <i>MiniportDevicePnPEventNotify</i> function with the 
    <b>DevicePnPEvent</b> member of the 
    <i>NetDevicePnPEvent</i> parameter set to
    <b>NdisDevicePnPEventPowerProfileChanged</b> after one of the following events:

<ul>
<li>
Driver initialization is complete.

</li>
<li>
The driver received an 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-set-power">OID_PNP_SET_POWER</a> notification that
      specifies the powered-on state (
      <b>NdisDeviceStateD0</b>).

</li>
</ul>
In the second case, the value at 
    <i>InformationBuffer</i> indicates whether the system is running on battery power (<b>NdisPowerProfileBattery</b>) or AC power (<b>NdisPowerProfileAcOnline</b>). A driver can use this information to adjust the power consumption of
    the specified miniport adapter. For example, the driver for a wireless LAN device could reduce power
    consumption if the system is running on battery power or increase power consumption if the system is
    running on AC power.

When a driver receives a surprise removal notification (the 
    <b>DevicePnPEvent</b> member of the 
    <i>NetDevicePnPEvent</i> parameter is 
    <b>NdisDevicePnPEventSurpriseRemoved</b>), it should:

<ul>
<li>
Note internally that the device has been removed.

</li>
<li>
Cancel any pending IRPs that it sent down to the underlying bus driver.

</li>
</ul>
After NDIS calls the 
    <i>MiniportDevicePnPEventNotify</i> function to indicate a surprise removal, NDIS
    calls the driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function. If the driver
    receives any send requests or OID requests before NDIS calls 
    <i>MiniportHaltEx</i>, it should immediately complete such requests with a status
    value of NDIS_STATUS_NOT_ACCEPTED.

NDIS calls 
    <i>MiniportDevicePnPEventNotify</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportDevicePnPEventNotify</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportDevicePnPEventNotify</i> function that is named "MyDevicePnPEventNotify", use the <b>MINIPORT_DEVICE_PNP_EVENT_NOTIFY</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_DEVICE_PNP_EVENT_NOTIFY MyDevicePnPEventNotify;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDevicePnPEventNotify(
    NDIS_HANDLE  MiniportAdapterContext,
    PNET_DEVICE_PNP_EVENT  NetDevicePnPEvent
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_DEVICE_PNP_EVENT_NOTIFY</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_DEVICE_PNP_EVENT_NOTIFY</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_device_pnp_event">NET_DEVICE_PNP_EVENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-pnp-set-power">OID_PNP_SET_POWER</a>

