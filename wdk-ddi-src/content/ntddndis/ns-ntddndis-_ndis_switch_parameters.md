---
UID: NS:ntddndis._NDIS_SWITCH_PARAMETERS
title: _NDIS_SWITCH_PARAMETERS (ntddndis.h)
description: The NDIS_SWITCH_PARAMETERS structure contains the configuration data for a Hyper-V extensible switch.
old-location: netvista\ndis_switch_parameters.htm
tech.root: netvista
ms.assetid: 766e042a-3f21-4f57-a780-83f92bef0a6c
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_PARAMETERS, NDIS_SWITCH_PARAMETERS, NDIS_SWITCH_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PARAMETERS, PNDIS_SWITCH_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PARAMETERS, netvista.ndis_switch_parameters, ntddndis/NDIS_SWITCH_PARAMETERS, ntddndis/PNDIS_SWITCH_PARAMETERS"
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PARAMETERS"
req.header: ntddndis.h
req.include-header: Ndis.h, Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
- ntddndis.h
api_name:
- NDIS_SWITCH_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PARAMETERS, *PNDIS_SWITCH_PARAMETERS
---

# _NDIS_SWITCH_PARAMETERS structure


## -description


The <b>NDIS_SWITCH_PARAMETERS</b> structure contains the configuration data for a Hyper-V extensible switch.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PARAMETERS</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PARAMETERS_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field SwitchName

 An <b>NDIS_SWITCH_NAME</b> value that specifies the unique internal name of the extensible switch.

The internal switch name is used by WMI-based policy management applications. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/managing-hyper-v-extensible-switch-extensibility-policies">Managing Hyper-V Extensible Switch Policies</a>.


### -field SwitchFriendlyName

 An <b>NDIS_SWITCH_FRIENDLYNAME</b> value that specifies the user-friendly description of the extensible switch.


### -field NumSwitchPorts

A UINT32 value that specifies the number of ports configured on the extensible switch.


### -field IsActive

A BOOLEAN that if TRUE indicates that the Hyper-V extensible switch activation has finished and it is safe to query for other switch configuration such as enumerating ports, NICs, and properties. If FALSE, the extension must wait for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event">NetEventSwitchActivate</a> PNP event to be issued before querying for switch configuration. 


## -remarks



The <b>NDIS_SWITCH_PARAMETERS</b> structure is used in the 
    OID request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-parameters">OID_SWITCH_PARAMETERS</a>.

This structure is also passed in the <i>vSwitch</i> parameter of the following callout functions for Windows Filtering Platform callout drivers:<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_interface_event_callback0">FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_lifetime_event_callback0">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_policy_event_callback0">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_port_event_callback0">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_runtime_state_save_callback0">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a>
</li>
</ul>


<div class="alert"><b>Note</b>  The <b>NDIS_SWITCH_NAME</b> and  <b>NDIS_SWITCH_FRIENDLYNAME</b> data types are type-defined by the <a href="https://docs.microsoft.com/windows/desktop/api/ifdef/ns-ifdef-_if_counted_string_lh">IF_COUNTED_STRING</a> structure. A string that is defined by this structure does not have to be null-terminated. However, the length of the string must be set in the <b>Length</b> member of this structure. If the string is null-terminated, the <b>Length</b> member must not include the terminating null character.

</div>
<div> </div>



## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_lifetime_event_callback0">FWPS_VSWITCH_LIFETIME_EVENT_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_policy_event_callback0">FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_port_event_callback0">FWPS_VSWITCH_PORT_EVENT_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0">FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_runtime_state_save_callback0">FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_vswitch_interface_event_callback0">IF_COUNTEDFWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event">NetEventSwitchActivate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-parameters">OID_SWITCH_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ifdef/ns-ifdef-_if_counted_string_lh">_STRING</a>
 

 

