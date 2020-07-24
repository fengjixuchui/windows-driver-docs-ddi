---
UID: NC:fwpsk.FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0
title: FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0 (fwpsk.h)
description: The filter engine calls the vSwitchInterfaceEventNotifyFn (FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0) callout function to notify the callout driver about events that are associated the virtual switch interface.Note  FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0 is a specific version of FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_interface_event_callback0.htm
tech.root: netvista
ms.assetid: 63EAA278-9CE6-4C75-8221-E1666F143815
ms.date: 05/02/2018
keywords: ["FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0 callback function"]
ms.keywords: FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0, FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0 callback, fwpsk/vSwitchInterfaceEventNotifyFn, netvista.fwps_vswitch_interface_event_callback0, vSwitchInterfaceEventNotifyFn, vSwitchInterfaceEventNotifyFn callback function [Network Drivers Starting with Windows Vista]
f1_keywords:
 - "fwpsk/vSwitchInterfaceEventNotifyFn"
 - "vSwitchInterfaceEventNotifyFn"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- fwpsk.h
api_name:
- vSwitchInterfaceEventNotifyFn
targetos: Windows
req.typenames: 
---

# FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0 callback function


## -description


The filter engine calls the <i>vSwitchInterfaceEventNotifyFn</i>  (<i>FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</i>) callout function to notify the callout driver about events that are associated the virtual switch  interface.

<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK</i>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>

## -parameters




### -param notifyContext [in, optional]

A pointer to a context provided by the callout driver. The driver passed this pointer to the <i>notifyContext</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>
 function. This parameter is optional and can be NULL.


### -param completionContext [in]

A pointer to a completion context provided by the callout driver. This parameter is optional and can be NULL.




### -param eventType [in]

The type of virtual switch event  specified as one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_vswitch_event_type_">FWPS_VSWITCH_EVENT_TYPE</a> enumeration values. For more information, see Remarks.


### -param vSwitch [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> structure that contains information about a virtual switch.


<div class="alert"><b>Note</b>  The information in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> structure reflects the initial state of the virtual switch, not necessarily its current state. In particular, the <b>NumSwitchPorts</b> and <b>IsActive</b> members might still have their initial value of zero, unless a virtual switch PnP event has been triggered. Current state information can be found in the other parameters to this callback function.</div>
<div> </div>

### -param vSwitchNic [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a> structure that specifies the parameters for a virtual miniport adapter that is connected to a virtual switch  port. 



## -returns



A callout's 
  
  <i>FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</i> function returns one of the following NTSTATUS codes.

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
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>
 




## -remarks



A callout driver registers a   
  <i>vSwitchInterfaceEventNotifyFn</i> function  by calling      
    the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>
 function.

If the <i>eventType</i> parameter  is set to WPS_VSWITCH_EVENT_INTERFACE_CREATE, a new network connection between a virtual switch port and a network adapter is completely established. The <i>vSwitchNic</i> parameter identifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a> structure that contains information about the virtual network adapter that is connected to the virtual switch port. 



   If the <i>eventType</i> parameter is FWPS_VSWITCH_EVENT_INTERFACE_DISCONNECT, the connection between a virtual switch port and a network adapter is being torn down. After the connection has been completely torn down, the WFP filter driver will  call <i>vSwitchInterfaceEventNotifyFn</i> with FWPS_VSWITCH_EVENT_INTERFACE_DELETE set in the <i>eventType</i> parameter.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">Callout Driver Callout Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_vswitch_event_type_">FWPS_VSWITCH_EVENT_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a>
 

 

