---
UID: NS:ntddndis._NDIS_NIC_SWITCH_PARAMETERS
title: _NDIS_NIC_SWITCH_PARAMETERS (ntddndis.h)
description: The NDIS_NIC_SWITCH_PARAMETERS structure specifies the configuration parameters of a network adapter switch on the network adapter.
old-location: netvista\ndis_nic_switch_parameters.htm
tech.root: netvista
ms.assetid: BC43A7DF-51B4-4571-86C5-12B332B13084
ms.date: 05/02/2018
keywords: ["NDIS_NIC_SWITCH_PARAMETERS structure"]
ms.keywords: "*PNDIS_NIC_SWITCH_PARAMETERS, NDIS_NIC_SWITCH_PARAMETERS, NDIS_NIC_SWITCH_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_PARAMETERS, PNDIS_NIC_SWITCH_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_PARAMETERS, netvista.ndis_nic_switch_parameters, ntddndis/NDIS_NIC_SWITCH_PARAMETERS, ntddndis/PNDIS_NIC_SWITCH_PARAMETERS"
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
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_PARAMETERS, *PNDIS_NIC_SWITCH_PARAMETERS
f1_keywords:
 - _NDIS_NIC_SWITCH_PARAMETERS
 - ntddndis/_NDIS_NIC_SWITCH_PARAMETERS
 - PNDIS_NIC_SWITCH_PARAMETERS
 - ntddndis/PNDIS_NIC_SWITCH_PARAMETERS
 - NDIS_NIC_SWITCH_PARAMETERS
 - ntddndis/NDIS_NIC_SWITCH_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_NIC_SWITCH_PARAMETERS
---

# _NDIS_NIC_SWITCH_PARAMETERS structure


## -description

The <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure specifies the configuration parameters of a network adapter switch on the network adapter.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_PARAMETERS_REVISION_1.

### -field Flags

 A ULONG value that contains a bitwise OR of flags. The following flags are defined for this member. 






#### NDIS_NIC_SWITCH_PARAMETERS_SWITCH_NAME_CHANGED

This flag specifies that the field that has been updated in the <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure is the <b>SwitchName</b> member.

<div class="alert"><b>Note</b>  This flag is valid only when this structure is used in an OID set request of <a href="/windows-hardware/drivers/network/oid-nic-switch-parameters">OID_NIC_SWITCH_PARAMETERS</a>. </div>
<div> </div>

### -field SwitchType

An 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_nic_switch_type">NDIS_NIC_SWITCH_TYPE</a> enumeration value that
     specifies the type of the network adapter switch.

<div class="alert"><b>Note</b>   Starting with Windows Server 2012, Windows only supports a switch type of <b>NdisNicSwitchTypeExternal</b>.  An external switch specifies that the ports connected to this type of switch can access the external network through the physical port on the network adapter. The default virtual port (VPort) on the external switch provides external network connectivity to the virtualization stack that runs in the management operating system of the Hyper-V parent partition.</div>
<div> </div>

### -field SwitchId

An NDIS_NIC_SWITCH_ID value that contains a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

### -field SwitchFriendlyName

An NDIS_NIC_SWITCH_FRIENDLY_NAME value that contains a description for the switch.

### -field NumVFs

A ULONG value that specifies the number of PCI Express (PCIe) Virtual Functions (VFs) that are enabled on the network adapter. VFs are enabled on the adapter when virtualization is enabled through a call to <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismenablevirtualization">NdisMEnableVirtualization</a>.

<div class="alert"><b>Note</b>  Before a VF can be attached to a Hyper-V child partition, resources must be allocated for it through an OID method request of <a href="/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>.</div>
<div> </div>

### -field NdisReserved1

Reserved for NDIS.

### -field NdisReserved2

Reserved for NDIS.

### -field NdisReserved3

Reserved for NDIS.

### -field NumQueuePairsForDefaultVPort

## -remarks

The <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure is used in OID method requests of <a href="/windows-hardware/drivers/network/oid-nic-switch-create-switch">OID_NIC_SWITCH_CREATE_SWITCH</a> and <a href="/windows-hardware/drivers/network/oid-nic-switch-parameters">OID_NIC_SWITCH_PARAMETERS</a>. These OID requests set or query the configuration parameters of a network adapter switch. 

For more information about the SR-IOV interface, see 	<a href="/windows-hardware/drivers/network/overview-of-single-root-i-o-virtualization--sr-iov-">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismenablevirtualization">NdisMEnableVirtualization</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-create-switch">OID_NIC_SWITCH_CREATE_SWITCH</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-parameters">OID_NIC_SWITCH_PARAMETERS</a>