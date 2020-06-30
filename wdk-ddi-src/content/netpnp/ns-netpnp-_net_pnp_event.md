---
UID: NS:netpnp._NET_PNP_EVENT
title: _NET_PNP_EVENT (netpnp.h)
description: The NET_PNP_EVENT structure describes a network Plug and Play (PnP) event, an NDIS PnP event, or a power management event.
old-location: netvista\net_pnp_event.htm
tech.root: netvista
ms.assetid: b68fb279-c1d4-4f0b-8b04-b17a01a65560
ms.date: 05/02/2018
keywords: ["_NET_PNP_EVENT structure"]
ms.keywords: "*PNET_PNP_EVENT, NET_PNP_EVENT, NET_PNP_EVENT structure [Network Drivers Starting with Windows Vista], PNET_PNP_EVENT, PNET_PNP_EVENT structure pointer [Network Drivers Starting with Windows Vista], _NET_PNP_EVENT, ndis/NET_PNP_EVENT, ndis/PNET_PNP_EVENT, netvista.net_pnp_event, protocol_structures_ref_0d2da286-4352-4097-901d-d3eba45d31c2.xml"
f1_keywords:
 - "netpnp/NET_PNP_EVENT"
req.header: netpnp.h
req.include-header: Ndis.h, Netpnp.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 5.1, and NDIS 6.0 and later. For more information about the NDIS 5.1 version of this structure, see    NET_PNP_EVENT (NDIS 5.1).
req.target-min-winversvr: 
req.kmdf-ver: 
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NET_PNP_EVENT
product:
- Windows
targetos: Windows
req.typenames: NET_PNP_EVENT, *PNET_PNP_EVENT
---

# _NET_PNP_EVENT structure


## -description


The <b>NET_PNP_EVENT</b> structure describes a network Plug and Play (PnP) event, an NDIS PnP event, or a
  power management event.


## -struct-fields




### -field NetEvent

An event code that describes the event as one of the following:
     





#### NetEventSetPower

Indicates that the power manager has sent a Set Power request, which specifies a transition to a
       system power state. NDIS translates this state to an appropriate device power state for the
       device.

For more information, see the Remarks section.



#### NetEventQueryPower

Indicates that the power manager has sent a Query Power request, which requests a transition to
       a system power state. NDIS translates this state to an appropriate device power state for the
       device.

For more information, see the Remarks section.



#### NetEventQueryRemoveDevice

Indicates that the PnP Manager has sent a Query Remove Device request. The PnP Manager sends
       this request to query whether a device can be removed without disrupting operations.



#### NetEventCancelRemoveDevice

Indicates that the PnP Manager has sent a Cancel Remove Device request. The PnP Manager sends
       this request to cancel the removal of a device after the PnP Manager sends a Query Remove Device request.



#### NetEventReconfigure

Indicates that the configuration has changed for a network component. For example, if a user,
       through the Network and Dial-up Connections folder, changes the IP address for TCP/IP, NDIS indicates
       the 
       <b>NetEventReconfigure</b> event to the TCP/IP protocol. Also, an intermediate driver typically uses
       this event as a trigger to call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiminitializedeviceinstanceex">
       NdisIMInitializeDeviceInstanceEx</a> function and start its virtual miniports. For more information
       about 
       <b>NetEventReconfigure</b>, see 
       NetEventIMReEnableDevice.



#### NetEventBindList

Indicates to a protocol driver that its bind list processing order has been reconfigured. This
       list indicates a relative order that applies to bindings when processing, for example, a user request
       that might be routed to one of several bindings. The buffer that is passed with this event contains a
       list of device names that are formatted as null-terminated Unicode strings. The format of each device
       name is identical to the 
       <b>AdapterName</b> member that is passed to a call to the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function.



#### NetEventBindsComplete

Indicates that a protocol driver has bound to all the NICs that it can bind to. NDIS will not
       indicate any more NICs to the protocol unless a PnP NIC is plugged into the system.



#### NetEventPnPCapabilities

Indicates that the user enabled or disabled the wake-up capabilities of the underlying adapter.
       (The binding is specified by the 
       <i>ProtocolBindingContext</i> parameter that is passed to the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">
       ProtocolNetPnPEvent</a> function.)



#### NetEventPause

Indicates that the specified protocol binding should enter the 
       Pausing state. The binding will enter the 
       Paused state after NDIS has completed all the outstanding send requests for the
       binding.



#### NetEventRestart

Indicates that the specified protocol binding has entered the 
       Restarting state. After the protocol driver is ready to resume send and receive operations for
       the binding, the binding enters the 
       Running state.



#### NetEventPortActivation

Indicates the activation of a list of ports that are associated with the specified
       binding.



#### NetEventPortDeactivation

Indicates the deactivation of a list of ports that are associated with the specified
       binding.



#### NetEventIMReEnableDevice

Indicates that the configuration has changed for a virtual miniport of an NDIS 6.0 or later
       intermediate driver. 
       <b>NetEventIMReEnableDevice</b> is similar to the 
       <b>NetEventReconfigure</b> event except that the intermediate driver receives this event for a single
       virtual miniport and the 
       <b>NetEventReconfigure</b> event applies to all the intermediate driver's virtual miniports. For
       example, an intermediate driver receives the 
       <b>NetEventIMReEnableDevice</b> event when a user disables and then enables a single virtual miniport
       from the Device Manager or another source. For examples of intermediate driver power management, see the 
    <a href="https://go.microsoft.com/fwlink/p/?LinkId=617916">NDIS MUX Intermediate Driver and Notify Object</a> driver sample available in the <a href="https://go.microsoft.com/fwlink/p/?LinkId=616507">Windows driver samples</a> repository on GitHub.



#### NetEventNDKEnable

Indicates that Network Direct Kernel (NDK) is currently enabled.



#### NetEventNDKDisable

Indicates that NDK is currently disabled.



#### NetEventFilterPreDetach

Indicates that a filter is about to be detached, so that the filter can perform any necessary cleanup that isn't possible in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a> handler (because the OID and indication paths are closed at that time).



#### NetEventBindFailed

Indicates that a binding event failure has occurred.



#### NetEventSwitchActivate

Indicates that the Hyper-V Extensible Switch has completed activation, and switch extensions can now safely query for further switch configuration. The indication is only used in the Hyper-V Extensible Switch stack, issued by the extension miniport. See <a href="https://docs.microsoft.com/windows-hardware/drivers/network/querying-the-hyper-v-extensible-switch-configuration">Querying the Hyper-V Extensible Switch Configuration</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> for more details. 



#### NetEventInhibitBindsAbove

A synchronous event that prevents other filters and protocols from binding to the miniport adapter. Any filters or protocols that were previously bound will be unbound before the event completes. The usage rules are below.

<ul>
<li>Avoid leaving the miniport adapter in the inhibit state, for longer than 1000 milliseconds.</li>
<li>This event can only be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> begins and must not be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> returns.</li>
<li>This event can only be issued when the miniport adapter is in a D0 state.</li>
<li>Because this event is blocking, it should not be issued by any context that would cause a deadlock.</li>
<li>Locks must not be held while issuing this event.</li>
<li>This event must be issued at PASSIVE_LEVEL.</li>
</ul>
This event is available starting with NDIS version 6.50
and must be used with V2 or later version of <b>NET_PNP_EVENT</b>. This event can optionally be issued by a miniport driver. Protocols and filters cannot receive this event or issue it.



#### NetEventAllowBindsAbove

An asynchronous event that reverses the effects of NetEventInhibitBindsAbove. The usage rules are below.

<ul>
<li>This event can only be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> begins and must not be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> returns.</li>
<li>This event can only be issued when the miniport adapter is in a D0 state.</li>
<li>Locks must not be held while issuing this event.</li>
<li>This event must be issued at PASSIVE_LEVEL.</li>
</ul>
This event is available starting with NDIS version 6.50 and must be used with V2 or later version of <b>NET_PNP_EVENT</b>. This event can optionally be issued by a miniport driver. Protocols and filters cannot receive this event or issue it.



#### NetEventRequirePause

A synchronous event that indicates the protocols and filters including the miniport adapter must be paused. The protocols and filters and the miniport adapter are guaranteed to be paused when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismnetpnpevent">NdisMNetPnPEvent</a> routine returns. The usage rules are below.

<ul>
<li>Avoid delaying between NetEventAllowStart and NetEventRequirePause events for longer than 1000 milliseconds to prevent delay in user applications.</li>
<li>This event can only be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> begins and must not be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> returns.</li>
<li>There is no guarantee that NDIS will call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> after this event is issued. In particular, if your miniport adapter is already paused, NDIS won't introduce an extra start-pause loop. This means that the amount of times <i>MiniportPause</i> called is not greater than, less than, or equal to the amount this event is issued.</li>
<li>Because this event is blocking, it should not be issued by any context that would cause a deadlock.</li>
<li>Locks must not be held while issuing this event.</li>
</ul>
This event is available starting with NDIS version 6.50 and must be used with V2 or later version of <b>NET_PNP_EVENT</b>. This event can optionally be issued by a miniport driver. Protocols and filters cannot receive this event or issue it.



#### NetEventAllowStart

An asynchronous event that indicates the protocols and filters including the miniport adapter does not need to be paused. The usage rules are below. There is no guaranteed pause state for any driver in the protocols and filters after the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismnetpnpevent">NdisMNetPnPEvent</a> routine returns. 

<ul>
<li>This event can only be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> begins and must not be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> returns.</li>
<li>Because this event is blocking, it should not be issued by any context that would cause a deadlock.</li>
<li>Locks must not be held while issuing this event.</li>
</ul>
This event is available starting with NDIS version 6.50 and must be used with V2 or later version of <b>NET_PNP_EVENT</b>. This event can optionally be issued by a miniport driver. Protocols and filters cannot receive this event or issue it.


### -field Buffer

The address of a buffer that contains information that is specific to the event indicated in the 
     <b>NetEvent</b> member. For each type of event, the buffer contains the following information:
     





#### NetEventSetPower

The buffer contains the device power state to which the device is transitioning.
       

When NDIS calls a protocol driver's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function,
       the device state is NDIS_DEVICE_POWER_STATE, which can be one of the following values:





##### NdisDeviceStateUnspecified

The network device does not support power management.



##### NdisDeviceStateD0

The fully powered state, in which the device delivers full functionality and
         performance.



##### NdisDeviceStateD1

A low-power state, in which transmit requests from the host are not honored by the device,
         data received by the device is not transferred to host memory, and no interrupts can occur. Some
         device context may be lost. Depending on the capabilities of the NIC and its miniport driver, the
         device might be able to generate a wake-up signal.



##### NdisDeviceStateD2

A low-power state that is similar to 
         <b>NdisDeviceStateD1</b>, except that more power and less context are typically saved and more time
         is required to transition to the fully powered state.



##### NdisDeviceStateD3

The off state, in which power has been fully removed from the device.

For protocol drivers, 
       <b>NdisDeviceStateD0</b> means that the NIC is fully powered and is available for normal operations.
       Any other device state means that the device is not fully powered and is not available for sending and
       receiving network data.



#### NetEventQueryPower

The buffer contains the device power state that is requested for the device. The device state is
       NDIS_DEVICE_POWER_STATE (which is described in the 
       <b>NetEventSetPower</b> value description).



#### NetEventQueryRemoveDevice

The buffer contents are <b>NULL</b>.



#### NetEventCancelRemoveDevice

The buffer contents are <b>NULL</b>.



#### NetEventReconfigure

The buffer can contain protocol-specific data. The protocol driver is responsible for validating
       this data.



#### NetEventBindList

The buffer contains a revised binding list for the network component that the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">
       NET_PNP_EVENT_NOTIFICATION</a> structure is being passed to. The bind list, which is a series of
       null-terminated Unicode strings, has a REG_MULTI_SZ format. Each of the strings is an adapter name.
       TDI clients that are bound to a protocol use this bind list to reorder their bindings. The protocol
       driver is responsible for validating this list.



#### NetEventBindsComplete

The buffer contents are <b>NULL</b>.



#### NetEventPnPCapabilities

The buffer is a ULONG that contains a bitmask. When the NDIS_DEVICE_WAKE_UP_ENABLE flag is set
       in the bitmask, the wake-up capabilities of the NIC are enabled. Otherwise, the NIC's wake-up
       capabilities are disabled. (The binding is specified by the 
       <i>ProtocolBindingContext</i> parameter that is passed to 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>.) When set
       to zero, this flag indicates that the NIC's wake-up capabilities are disabled.



#### NetEventPause

The buffer contains an 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_pause_parameters">
       NDIS_PROTOCOL_PAUSE_PARAMETERS</a> structure.



#### NetEventRestart

The buffer might contain NULL or an 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_restart_parameters">
       NDIS_PROTOCOL_RESTART_PARAMETERS</a> structure. NDIS provides a pointer to an 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_attributes">NDIS_RESTART_ATTRIBUTES</a> structure
       in the 
       <b>RestartAttributes</b> member of the NDIS_PROTOCOL_RESTART_PARAMETERS structure. 

<div class="alert"><b>Note</b>  If the buffer is NULL, the restart attributes have not changed since the previous restart.</div>
<div> </div>


#### NetEventPortActivation

The buffer contains the first entry in a list of 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_port">NDIS_PORT</a> structures that identify the ports
       that NDIS will activate. You can use the 
       <b>Next</b> member of the NDIS_PORT structure to get the next structure in the list.



#### NetEventPortDeactivation

The buffer contains an array of port numbers, of type NDIS_PORT_NUMBER (defined as ULONG), that
       identify the NDIS ports that NDIS will deactivate. To calculate the number of elements in the array,
       divide the value of the 
       <b>BufferLength</b> member, which is in the <b>NET_PNP_EVENT</b> structure that is specified in the 
       <b>NetPnPEvent</b> member of 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">NET_PNP_EVENT_NOTIFICATION</a>,
       by 
       sizeof(NDIS_PORT_NUMBER).



#### NetEventIMReEnableDevice

The buffer contains a pointer to a variable of type NDIS_STRING that contains a null-terminated
       Unicode string that names the device object of a virtual miniport for the device that is being
       enabled. The string is a full path name—for example, 
       \Device\\<i>DeviceName</i>.



#### NetEventNDKEnable

The <b>Buffer</b> member is <b>NULL</b>.



#### NetEventNDKDisable

The <b>Buffer</b> member is <b>NULL</b>.



#### NetEventFilterPreDetach

The <b>Buffer</b> member is <b>NULL</b>.



#### NetEventBindFailed

The buffer contains an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_failed_notification">NDIS_BIND_FAILED_NOTIFICATION</a> structure.



#### NetEventSwitchActivate

The buffer contents are NULL.



#### NetEventAllowBindsAbove

The buffer contents are NULL.



#### NetEventInhibitBindsAbove

The buffer contents are NULL.



#### NetEventAllowStart

The buffer contents are NULL.



#### NetEventRequirePause

The buffer contents are NULL.


### -field BufferLength

The number of bytes of event-specific information at 
     <b>Buffer</b>.


### -field NdisReserved

An area reserved for used by NDIS.


### -field TransportReserved

An area reserved for used by the transport driver.


### -field TdiReserved

An area reserved for used by TDI.


### -field TdiClientReserved

An area reserved for used by a TDI client.


##### - Buffer.NetEventAllowBindsAbove

The buffer contents are NULL.


##### - Buffer.NetEventAllowStart

The buffer contents are NULL.


##### - Buffer.NetEventBindFailed

The buffer contains an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_failed_notification">NDIS_BIND_FAILED_NOTIFICATION</a> structure.


##### - Buffer.NetEventBindList

The buffer contains a revised binding list for the network component that the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">
       NET_PNP_EVENT_NOTIFICATION</a> structure is being passed to. The bind list, which is a series of
       null-terminated Unicode strings, has a REG_MULTI_SZ format. Each of the strings is an adapter name.
       TDI clients that are bound to a protocol use this bind list to reorder their bindings. The protocol
       driver is responsible for validating this list.


##### - Buffer.NetEventBindsComplete

The buffer contents are <b>NULL</b>.


##### - Buffer.NetEventCancelRemoveDevice

The buffer contents are <b>NULL</b>.


##### - Buffer.NetEventFilterPreDetach

The <b>Buffer</b> member is <b>NULL</b>.


##### - Buffer.NetEventIMReEnableDevice

The buffer contains a pointer to a variable of type NDIS_STRING that contains a null-terminated
       Unicode string that names the device object of a virtual miniport for the device that is being
       enabled. The string is a full path name—for example, 
       \Device\\<i>DeviceName</i>.


##### - Buffer.NetEventInhibitBindsAbove

The buffer contents are NULL.


##### - Buffer.NetEventNDKDisable

The <b>Buffer</b> member is <b>NULL</b>.


##### - Buffer.NetEventNDKEnable

The <b>Buffer</b> member is <b>NULL</b>.


##### - Buffer.NetEventPause

The buffer contains an 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_pause_parameters">
       NDIS_PROTOCOL_PAUSE_PARAMETERS</a> structure.


##### - Buffer.NetEventPnPCapabilities

The buffer is a ULONG that contains a bitmask. When the NDIS_DEVICE_WAKE_UP_ENABLE flag is set
       in the bitmask, the wake-up capabilities of the NIC are enabled. Otherwise, the NIC's wake-up
       capabilities are disabled. (The binding is specified by the 
       <i>ProtocolBindingContext</i> parameter that is passed to 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>.) When set
       to zero, this flag indicates that the NIC's wake-up capabilities are disabled.


##### - Buffer.NetEventPortActivation

The buffer contains the first entry in a list of 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_port">NDIS_PORT</a> structures that identify the ports
       that NDIS will activate. You can use the 
       <b>Next</b> member of the NDIS_PORT structure to get the next structure in the list.


##### - Buffer.NetEventPortDeactivation

The buffer contains an array of port numbers, of type NDIS_PORT_NUMBER (defined as ULONG), that
       identify the NDIS ports that NDIS will deactivate. To calculate the number of elements in the array,
       divide the value of the 
       <b>BufferLength</b> member, which is in the <b>NET_PNP_EVENT</b> structure that is specified in the 
       <b>NetPnPEvent</b> member of 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">NET_PNP_EVENT_NOTIFICATION</a>,
       by 
       sizeof(NDIS_PORT_NUMBER).


##### - Buffer.NetEventQueryPower

The buffer contains the device power state that is requested for the device. The device state is
       NDIS_DEVICE_POWER_STATE (which is described in the 
       <b>NetEventSetPower</b> value description).


##### - Buffer.NetEventQueryRemoveDevice

The buffer contents are <b>NULL</b>.


##### - Buffer.NetEventReconfigure

The buffer can contain protocol-specific data. The protocol driver is responsible for validating
       this data.


##### - Buffer.NetEventRequirePause

The buffer contents are NULL.


##### - Buffer.NetEventRestart

The buffer might contain NULL or an 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_restart_parameters">
       NDIS_PROTOCOL_RESTART_PARAMETERS</a> structure. NDIS provides a pointer to an 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_attributes">NDIS_RESTART_ATTRIBUTES</a> structure
       in the 
       <b>RestartAttributes</b> member of the NDIS_PROTOCOL_RESTART_PARAMETERS structure. 

<div class="alert"><b>Note</b>  If the buffer is NULL, the restart attributes have not changed since the previous restart.</div>
<div> </div>

##### - Buffer.NetEventSetPower

The buffer contains the device power state to which the device is transitioning.
       

When NDIS calls a protocol driver's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function,
       the device state is NDIS_DEVICE_POWER_STATE, which can be one of the following values:





##### NetEventSetPower.NdisDeviceStateUnspecified

The network device does not support power management.



##### NetEventSetPower.NdisDeviceStateD0

The fully powered state, in which the device delivers full functionality and
         performance.



##### NetEventSetPower.NdisDeviceStateD1

A low-power state, in which transmit requests from the host are not honored by the device,
         data received by the device is not transferred to host memory, and no interrupts can occur. Some
         device context may be lost. Depending on the capabilities of the NIC and its miniport driver, the
         device might be able to generate a wake-up signal.



##### NetEventSetPower.NdisDeviceStateD2

A low-power state that is similar to 
         <b>NdisDeviceStateD1</b>, except that more power and less context are typically saved and more time
         is required to transition to the fully powered state.



##### NetEventSetPower.NdisDeviceStateD3

The off state, in which power has been fully removed from the device.

For protocol drivers, 
       <b>NdisDeviceStateD0</b> means that the NIC is fully powered and is available for normal operations.
       Any other device state means that the device is not fully powered and is not available for sending and
       receiving network data.


##### - Buffer.NetEventSwitchActivate

The buffer contents are NULL.


##### - NetEvent.NetEventAllowBindsAbove

An asynchronous event that reverses the effects of NetEventInhibitBindsAbove. The usage rules are below.

<ul>
<li>This event can only be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> begins and must not be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> returns.</li>
<li>This event can only be issued when the miniport adapter is in a D0 state.</li>
<li>Locks must not be held while issuing this event.</li>
<li>This event must be issued at PASSIVE_LEVEL.</li>
</ul>
This event is available starting with NDIS version 6.50 and must be used with V2 or later version of <b>NET_PNP_EVENT</b>. This event can optionally be issued by a miniport driver. Protocols and filters cannot receive this event or issue it.


##### - NetEvent.NetEventAllowStart

An asynchronous event that indicates the protocols and filters including the miniport adapter does not need to be paused. The usage rules are below. There is no guaranteed pause state for any driver in the protocols and filters after the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismnetpnpevent">NdisMNetPnPEvent</a> routine returns. 

<ul>
<li>This event can only be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> begins and must not be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> returns.</li>
<li>Because this event is blocking, it should not be issued by any context that would cause a deadlock.</li>
<li>Locks must not be held while issuing this event.</li>
</ul>
This event is available starting with NDIS version 6.50 and must be used with V2 or later version of <b>NET_PNP_EVENT</b>. This event can optionally be issued by a miniport driver. Protocols and filters cannot receive this event or issue it.


##### - NetEvent.NetEventBindFailed

Indicates that a binding event failure has occurred.


##### - NetEvent.NetEventBindList

Indicates to a protocol driver that its bind list processing order has been reconfigured. This
       list indicates a relative order that applies to bindings when processing, for example, a user request
       that might be routed to one of several bindings. The buffer that is passed with this event contains a
       list of device names that are formatted as null-terminated Unicode strings. The format of each device
       name is identical to the 
       <b>AdapterName</b> member that is passed to a call to the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function.


##### - NetEvent.NetEventBindsComplete

Indicates that a protocol driver has bound to all the NICs that it can bind to. NDIS will not
       indicate any more NICs to the protocol unless a PnP NIC is plugged into the system.


##### - NetEvent.NetEventCancelRemoveDevice

Indicates that the PnP Manager has sent a Cancel Remove Device request. The PnP Manager sends
       this request to cancel the removal of a device after the PnP Manager sends a Query Remove Device request.


##### - NetEvent.NetEventFilterPreDetach

Indicates that a filter is about to be detached, so that the filter can perform any necessary cleanup that isn't possible in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a> handler (because the OID and indication paths are closed at that time).


##### - NetEvent.NetEventIMReEnableDevice

Indicates that the configuration has changed for a virtual miniport of an NDIS 6.0 or later
       intermediate driver. 
       <b>NetEventIMReEnableDevice</b> is similar to the 
       <b>NetEventReconfigure</b> event except that the intermediate driver receives this event for a single
       virtual miniport and the 
       <b>NetEventReconfigure</b> event applies to all the intermediate driver's virtual miniports. For
       example, an intermediate driver receives the 
       <b>NetEventIMReEnableDevice</b> event when a user disables and then enables a single virtual miniport
       from the Device Manager or another source. For examples of intermediate driver power management, see the 
    <a href="https://go.microsoft.com/fwlink/p/?LinkId=617916">NDIS MUX Intermediate Driver and Notify Object</a> driver sample available in the <a href="https://go.microsoft.com/fwlink/p/?LinkId=616507">Windows driver samples</a> repository on GitHub.


##### - NetEvent.NetEventInhibitBindsAbove

A synchronous event that prevents other filters and protocols from binding to the miniport adapter. Any filters or protocols that were previously bound will be unbound before the event completes. The usage rules are below.

<ul>
<li>Avoid leaving the miniport adapter in the inhibit state, for longer than 1000 milliseconds.</li>
<li>This event can only be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> begins and must not be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> returns.</li>
<li>This event can only be issued when the miniport adapter is in a D0 state.</li>
<li>Because this event is blocking, it should not be issued by any context that would cause a deadlock.</li>
<li>Locks must not be held while issuing this event.</li>
<li>This event must be issued at PASSIVE_LEVEL.</li>
</ul>
This event is available starting with NDIS version 6.50
and must be used with V2 or later version of <b>NET_PNP_EVENT</b>. This event can optionally be issued by a miniport driver. Protocols and filters cannot receive this event or issue it.


##### - NetEvent.NetEventNDKDisable

Indicates that NDK is currently disabled.


##### - NetEvent.NetEventNDKEnable

Indicates that Network Direct Kernel (NDK) is currently enabled.


##### - NetEvent.NetEventPause

Indicates that the specified protocol binding should enter the 
       Pausing state. The binding will enter the 
       Paused state after NDIS has completed all the outstanding send requests for the
       binding.


##### - NetEvent.NetEventPnPCapabilities

Indicates that the user enabled or disabled the wake-up capabilities of the underlying adapter.
       (The binding is specified by the 
       <i>ProtocolBindingContext</i> parameter that is passed to the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">
       ProtocolNetPnPEvent</a> function.)


##### - NetEvent.NetEventPortActivation

Indicates the activation of a list of ports that are associated with the specified
       binding.


##### - NetEvent.NetEventPortDeactivation

Indicates the deactivation of a list of ports that are associated with the specified
       binding.


##### - NetEvent.NetEventQueryPower

Indicates that the power manager has sent a Query Power request, which requests a transition to
       a system power state. NDIS translates this state to an appropriate device power state for the
       device.

For more information, see the Remarks section.


##### - NetEvent.NetEventQueryRemoveDevice

Indicates that the PnP Manager has sent a Query Remove Device request. The PnP Manager sends
       this request to query whether a device can be removed without disrupting operations.


##### - NetEvent.NetEventReconfigure

Indicates that the configuration has changed for a network component. For example, if a user,
       through the Network and Dial-up Connections folder, changes the IP address for TCP/IP, NDIS indicates
       the 
       <b>NetEventReconfigure</b> event to the TCP/IP protocol. Also, an intermediate driver typically uses
       this event as a trigger to call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiminitializedeviceinstanceex">
       NdisIMInitializeDeviceInstanceEx</a> function and start its virtual miniports. For more information
       about 
       <b>NetEventReconfigure</b>, see 
       NetEventIMReEnableDevice.


##### - NetEvent.NetEventRequirePause

A synchronous event that indicates the protocols and filters including the miniport adapter must be paused. The protocols and filters and the miniport adapter are guaranteed to be paused when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismnetpnpevent">NdisMNetPnPEvent</a> routine returns. The usage rules are below.

<ul>
<li>Avoid delaying between NetEventAllowStart and NetEventRequirePause events for longer than 1000 milliseconds to prevent delay in user applications.</li>
<li>This event can only be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> begins and must not be issued after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> returns.</li>
<li>There is no guarantee that NDIS will call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> after this event is issued. In particular, if your miniport adapter is already paused, NDIS won't introduce an extra start-pause loop. This means that the amount of times <i>MiniportPause</i> called is not greater than, less than, or equal to the amount this event is issued.</li>
<li>Because this event is blocking, it should not be issued by any context that would cause a deadlock.</li>
<li>Locks must not be held while issuing this event.</li>
</ul>
This event is available starting with NDIS version 6.50 and must be used with V2 or later version of <b>NET_PNP_EVENT</b>. This event can optionally be issued by a miniport driver. Protocols and filters cannot receive this event or issue it.


##### - NetEvent.NetEventRestart

Indicates that the specified protocol binding has entered the 
       Restarting state. After the protocol driver is ready to resume send and receive operations for
       the binding, the binding enters the 
       Running state.


##### - NetEvent.NetEventSetPower

Indicates that the power manager has sent a Set Power request, which specifies a transition to a
       system power state. NDIS translates this state to an appropriate device power state for the
       device.

For more information, see the Remarks section.


##### - NetEvent.NetEventSwitchActivate

Indicates that the Hyper-V Extensible Switch has completed activation, and switch extensions can now safely query for further switch configuration. The indication is only used in the Hyper-V Extensible Switch stack, issued by the extension miniport. See <a href="https://docs.microsoft.com/windows-hardware/drivers/network/querying-the-hyper-v-extensible-switch-configuration">Querying the Hyper-V Extensible Switch Configuration</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> for more details. 


## -remarks



In NDIS 6.0 and later versions, when the operating system issues a system PnP event or a power
    management event to a target device object that represents a miniport adapter, NDIS translates the event
    into a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">
    NET_PNP_EVENT_NOTIFICATION</a> structure. The 
    <b>NetPnPEvent</b> member of the <b>NET_PNP_EVENT_NOTIFICATION</b> structure is a <b>NET_PNP_EVENT</b> structure.

NDIS passes a pointer to the <b>NET_PNP_EVENT</b> structure to each protocol driver that is bound to the
    miniport adapter by calling the protocol driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function. The
    protocol driver should save this pointer, because the pointer is an input parameter to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompletenetpnpevent">NdisCompleteNetPnPEvent</a> function,
    which the driver calls to complete the call to 
    <i>ProtocolNetPnPEvent</i> asynchronously.

NDIS passes a pointer to the <b>NET_PNP_EVENT</b> structure to each filter driver that is bound to the
    miniport adapter by calling the filter driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_net_pnp_event">FilterNetPnPEvent</a> function. The
    filter driver does not have to save this pointer because the driver must complete the call to 
    <i>FilterNetPnPEvent</i> synchronously.

Starting with NDIS 6.30, the  protocol or filter driver must follow these guidelines when NDIS calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_net_pnp_event">FilterNetPnPEvent</a> functions:

<ul>
<li>
If the <b>NetEvent</b> member of the <b>NET_PNP_EVENT</b> structure is set to <b>NetEventSetPower</b>, the driver must stop generating new I/O requests. Also, the driver must not wait for the completion of any pending I/O requests.

After the protocol or filter driver  returns from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_net_pnp_event">FilterNetPnPEvent</a>, NDIS will not pause and restart these drivers during power-state transitions if the following conditions are true:

<ul>
<li>
The underlying miniport driver sets the <b>NDIS_MINIPORT_ATTRIBUTES_NO_PAUSE_ON_SUSPEND</b> flag in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure. The driver passes a pointer to this structure in its call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a> function.


</li>
<li>
All filter drivers that are attached to the miniport driver support NDIS 6.30 or later versions of NDIS.

</li>
<li>
All protocol drivers that are bound to the miniport driver support NDIS 6.30 or later versions of NDIS.

</li>
</ul>
</li>
<li>
If the <b>NetEvent</b> member of the <b>NET_PNP_EVENT</b> structure is set to <b>NetEventSetPower</b> or <b>NetEventQueryPower</b>, the driver must not wait for the completion of any pending I/O requests.

</li>
</ul>
The 
    <b>NetEvent</b> member in the <b>NET_PNP_EVENT</b> structure identifies the type of Plug and Play or power
    management event. The 
    <b>Buffer</b> contains information that is specific to the type of event.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_net_pnp_event">FilterNetPnPEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_failed_notification">NDIS_BIND_FAILED_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_port">NDIS_PORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_pause_parameters">
   NDIS_PROTOCOL_PAUSE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_restart_parameters">
   NDIS_PROTOCOL_RESTART_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_attributes">NDIS_RESTART_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">NET_PNP_EVENT_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompletenetpnpevent">NdisCompleteNetPnPEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiminitializedeviceinstanceex">
   NdisIMInitializeDeviceInstanceEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/querying-the-hyper-v-extensible-switch-configuration">Querying the Hyper-V Extensible Switch Configuration</a>
 

 

