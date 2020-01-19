---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_VLAN
title: _NDIS_SWITCH_PORT_PROPERTY_VLAN (ntddndis.h)
description: The NDIS_SWITCH_PORT_PROPERTY_VLAN structure specifies a virtual local area network (VLAN) policy property for a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_property_vlan.htm
tech.root: netvista
ms.assetid: 2A151351-AC57-4F7C-BA1A-201F6FB29C4F
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_VLAN, NDIS_SWITCH_PORT_PROPERTY_VLAN, NDIS_SWITCH_PORT_PROPERTY_VLAN structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PROPERTY_VLAN, PNDIS_SWITCH_PORT_PROPERTY_VLAN structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_VLAN, netvista.ndis_switch_port_property_vlan, ntddndis/NDIS_SWITCH_PORT_PROPERTY_VLAN, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_VLAN"
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_SWITCH_PORT_PROPERTY_VLAN"
req.header: ntddndis.h
req.include-header: Ndis.h
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
- Ntddndis.h
api_name:
- NDIS_SWITCH_PORT_PROPERTY_VLAN
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PROPERTY_VLAN, *PNDIS_SWITCH_PORT_PROPERTY_VLAN
---

# _NDIS_SWITCH_PORT_PROPERTY_VLAN structure


## -description


The <b>NDIS_SWITCH_PORT_PROPERTY_VLAN</b> structure specifies a virtual local area network (VLAN) policy property for a Hyper-V extensible switch port.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_VLAN</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_VLAN</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:





#### NDIS_SWITCH_PORT_PROPERTY_VLAN_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_VLAN_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.


### -field OperationMode

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_vlan_mode">NDIS_SWITCH_PORT_VLAN_MODE</a> enumeration value that specifies the operation mode of the VLAN.


### -field VlanProperties

A structure that specifies the properties of a VLAN with an operation mode of <b>NdisSwitchPortVlanModeAccess</b> or <b>NdisSwitchPortVlanModeTrunk</b>. This structure contains the following members:



### -field VlanProperties.AccessVlanId

A UINT16 value that specifies the VLAN identifier for the extensible switch port that operates in VLAN access mode.

<div class="alert"><b>Note</b>  This member is only valid if  the <b>OperationMode</b> member is set to <b>NdisSwitchPortVlanModeAccess</b>.</div>
<div> </div>

### -field VlanProperties.NativeVlanId

A UINT16 value that specifies the VLAN identifier for the extensible switch port that operates in VLAN trunk mode.


### -field VlanProperties.PruneVlanIdArray

An array of UINT64 elements that specifies VLAN identifiers whose packets are blocked on an extensible switch port.

The array has 64 UINT64 elements that represent 4096 consecutive bits.
         Each bit that has a value of one specifies a VLAN identifier whose packets are blocked from being sent or received on an extensible switch port. For example,  if bit three is set to one, packet traffic from VLAN identifier three is blocked on a port. Similarly, if bit 64 is set to zero, packet traffic from VLAN identifier 64 is not blocked on a port.


<div class="alert"><b>Note</b>  VLANS with identifiers that map to a bit value of one are
        always blocked. This overrides the equivalent bit setting for the VLAN identifier in the <b>TrunkVlanIdArray</b> member.</div>
<div> </div>

### -field VlanProperties.TrunkVlanIdArray

An array of UINT64 elements that specifies VLAN identifiers whose packets are allowed on an extensible switch port.

The array has 64 UINT64 elements that represent 4096 consecutive bits.
         Each bit that has a value of one specifies a VLAN identifier whose packets are allowed to be sent or received on an extensible switch port. For example,  if bit two is set to one, packet traffic from VLAN identifier two is allowed on a port. Similarly, if bit 1954 is set to zero, packet traffic from VLAN identifier 1954 is not allowed on a port.



### -field PvlanProperties

A structure that specifies the properties of a VLAN with an operation mode of <b>NdisSwitchPortVlanModePrivate</b>. This structure contains the following members:


### -field PvlanProperties.PvlanMode

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_pvlan_mode">NDIS_SWITCH_PORT_PVLAN_MODE</a> enumeration value that specifies the operation mode of the PVLAN.


### -field PvlanProperties.PrimaryVlanId

A UINT16 value that specifies the primary VLAN identifier for an extensible switch port.

<div class="alert"><b>Note</b>  This member is only valid if   the <b>PvlanMode</b> member is set to <b>NdisSwitchPortPvlanModeCommunity</b>.</div>
<div> </div>

### -field PvlanProperties.SecondaryVlanId

A UINT16 value that specifies the secondary VLAN identifier for an extensible switch port.

<div class="alert"><b>Note</b>  This member is only valid if   the  <b>PvlanMode</b> member is set to <b>NdisSwitchPortPvlanModeIsolated</b> or <b>NdisSwitchPortPvlanModeCommunity</b>.</div>
<div> </div>

### -field PvlanProperties.SecondaryVlanIdArray

An array of UINT64 elements that specify the secondary VLAN identifiers for an extensible switch port.

The array has 64 UINT64 elements, which represent 4096 consecutive bits.
         Each bit that has a value of one specifies a secondary VLAN identifier for the extensible switch port. For example,  if bit five is set to one, the secondary VLAN identifier is five. Similarly, if bit 128 is set to zero, 128 cannot be used as a secondary VLAN identifier.


<div class="alert"><b>Note</b>  This member is only valid if   the <b>PvlanMode</b> member is set to <b>NdisSwitchPortPvlanModePromiscuous</b>.</div>
<div> </div>

#### - SupportedModes

A UINT64 value that contains a bitwise OR of the flags that specify the VLAN operation modes that are supported on the extensible switch port. The following bits specify the supported operation modes:





#### Bit 0

Specifies a VLAN access operation mode in which packets from a single VLAN can be sent or received over the port. These packets could be forwarded from other ports on the extensible switch.





#### Bit 1

Specifies a VLAN truck operation mode where packets from multiple VLANs and non-VLAN packets can be sent or received over the port. These packets could be forwarded from other ports on the extensible switch.





#### Bit 2

Specifies an operation mode where packets from a single VLAN can be sent or received over the port. These packets cannot be forwarded from other ports on the extensible switch.




## -remarks



The <b>NDIS_SWITCH_PORT_PROPERTY_VLAN</b> structure is used in the following OID set requests: 

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-add">OID_SWITCH_PORT_PROPERTY_ADD</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-update">OID_SWITCH_PORT_PROPERTY_UPDATE</a>


</li>
</ul>
The <b>NDIS_SWITCH_PORT_PROPERTY_VLAN</b> structure follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_parameters">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure in the buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this buffer.

Port properties, such as <b>NDIS_SWITCH_PORT_PROPERTY_VLAN</b>, are enforced by the extensible switch extension that is installed as a forwarding extension. This type of extension enforces its own rules for forwarding packets, OIDs, and status indications through the extensible switch driver stack.  There can be only one forwarding extension per each instance of an extensible switch.

For more information on forwarding extensions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/forwarding-extensions">Forwarding Extensions</a>.

<div class="alert"><b>Note</b>  If a forwarding extension is not installed, the extensible switch interface enforces the port property itself.</div>
<div> </div>



## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_port_property_parameters">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_switch_port_vlan_mode">NDIS_SWITCH_PORT_VLAN_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-add">OID_SWITCH_PORT_PROPERTY_ADD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-property-update">OID_SWITCH_PORT_PROPERTY_UPDATE</a>
 

 

