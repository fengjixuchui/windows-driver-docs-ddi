---
UID: NC:fwpsk.FWPS_VSWITCH_PORT_EVENT_CALLBACK0
title: FWPS_VSWITCH_PORT_EVENT_CALLBACK0 (fwpsk.h)
description: The filter engine calls the vSwitchPortEventNotifyFn (FWPS_VSWITCH_PORT_EVENT_CALLBACK0) callout function to notify the callout driver about events that are associated a virtual switch (vSwitch) port.Note  FWPS_VSWITCH_PORT_EVENT_CALLBACK0 is a specific version of FWPS_VSWITCH_PORT_EVENT_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_port_event_callback0.htm
tech.root: netvista
ms.assetid: CE4B14BE-5ECA-4C2F-809C-B0DC27EC2FF2
ms.date: 05/02/2018
keywords: ["FWPS_VSWITCH_PORT_EVENT_CALLBACK0 callback function"]
ms.keywords: FWPS_VSWITCH_PORT_EVENT_CALLBACK0, FWPS_VSWITCH_PORT_EVENT_CALLBACK0 callback, fwpsk/vSwitchPortEventNotifyFn, netvista.fwps_vswitch_port_event_callback0, vSwitchPortEventNotifyFn, vSwitchPortEventNotifyFn callback function [Network Drivers Starting with Windows Vista]
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FWPS_VSWITCH_PORT_EVENT_CALLBACK0
 - fwpsk/FWPS_VSWITCH_PORT_EVENT_CALLBACK0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fwpsk.h
api_name:
 - vSwitchPortEventNotifyFn
---

# FWPS_VSWITCH_PORT_EVENT_CALLBACK0 callback function


## -description

The filter engine calls the <i>vSwitchPortEventNotifyFn</i>   (<i>FWPS_VSWITCH_PORT_EVENT_CALLBACK0</i>) callout function to notify the callout driver about events that are
  associated a virtual switch (vSwitch) port.<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_PORT_EVENT_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_PORT_EVENT_CALLBACK</i>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>

## -parameters

### -param notifyContext 

[in, optional]
A pointer to a context provided by the callout driver. The driver passed this pointer to the <i>notifyContext</i> parameter of the <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>
 function. This parameter is optional and can be NULL.

### -param completionContext 

[in]
A pointer to a completion context provided by the callout driver. This parameter is optional and can be NULL.

### -param eventType 

[in]
The type of virtual switch vSwitch event  specified as one of the <a href="/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_vswitch_event_type_">FWPS_VSWITCH_EVENT_TYPE</a> enumeration values. For more information, see Remarks.

### -param vSwitch 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> structure that contains information about a virtual switch.
  


<div class="alert"><b>Note</b>  The information in the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> structure reflects the initial state of the virtual switch, not necessarily its current state. In particular, the <b>NumSwitchPorts</b> and <b>IsActive</b> members might still have their initial value of zero, unless a virtual switch PnP event has been triggered. Current state information can be found in the other parameters to this callback function.</div>
<div> </div>

### -param vSwitchPort 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> structure that contains  parameters for a port on a vSwitch.

## -returns

A callout's 
  
  <i>FWPS_VSWITCH_PORT_EVENT_CALLBACK0</i> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callout driver accepts the notification from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later.  The callout  driver will  call the <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitchnotifycomplete0">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>

## -remarks

A callout driver registers a <i>vSwitchPortEventNotifyFn</i> function  by calling  the <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>
 function.

If the <i>vSwitchPortEventNotifyFn</i> callback is registered, the callout driver receives notifications  for port creation and deletion.

If the <i>eventType</i> parameter  is set to FWPS_VSWITCH_EVENT_PORT_CREATE, a vSwitch port was created. 
In this case, the <i>vSwitch</i> parameter identifies an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> structure that contains information about the virtual switch (vSwitch) and the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> parameter contains information about the port. 


A callout can return STATUS_PENDING from <i>vSwitchPortEventNotifyFn</i>. In this case, the callout  driver calls the <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitchnotifycomplete0">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.

After the port is deleted, the WFP filter driver calls <i>vSwitchPortEventNotifyFn</i> with FWPS_VSWITCH_EVENT_PORT_DELETE set in the <i>eventType</i> parameter.

## -see-also

<a href="/windows-hardware/drivers/ddi/_netvista/">Callout Driver Callout Functions</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_vswitch_event_type_">FWPS_VSWITCH_EVENT_TYPE</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitchnotifycomplete0">FwpsvSwitchNotifyComplete0</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a>