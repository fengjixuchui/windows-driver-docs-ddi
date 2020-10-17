---
UID: NS:ntddndis._NDIS_SWITCH_NIC_ARRAY
title: _NDIS_SWITCH_NIC_ARRAY (ntddndis.h)
description: The NDIS_SWITCH_NIC_ARRAY structure specifies an array of network adapter configuration parameters.
old-location: netvista\ndis_switch_nic_array.htm
tech.root: netvista
ms.assetid: 3509a177-d974-45fb-9387-21780483cbe7
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_NIC_ARRAY structure"]
ms.keywords: "*PNDIS_SWITCH_NIC_ARRAY, NDIS_SWITCH_NIC_ARRAY, NDIS_SWITCH_NIC_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_NIC_ARRAY, PNDIS_SWITCH_NIC_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_NIC_ARRAY, netvista.ndis_switch_nic_array, ntddndis/NDIS_SWITCH_NIC_ARRAY, ntddndis/PNDIS_SWITCH_NIC_ARRAY"
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
targetos: Windows
req.typenames: NDIS_SWITCH_NIC_ARRAY, *PNDIS_SWITCH_NIC_ARRAY
f1_keywords:
 - _NDIS_SWITCH_NIC_ARRAY
 - ntddndis/_NDIS_SWITCH_NIC_ARRAY
 - PNDIS_SWITCH_NIC_ARRAY
 - ntddndis/PNDIS_SWITCH_NIC_ARRAY
 - NDIS_SWITCH_NIC_ARRAY
 - ntddndis/NDIS_SWITCH_NIC_ARRAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_SWITCH_NIC_ARRAY
---

# _NDIS_SWITCH_NIC_ARRAY structure


## -description

The <b>NDIS_SWITCH_NIC_ARRAY</b> structure specifies an array of  network adapter configuration parameters. Each element in the array specifies the parameters for a  network adapter that is connected to a port on a Hyper-V extensible switch. Each element is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a> structure.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_NIC_ARRAY</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_NIC_ARRAY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_NIC_ARRAY_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_NIC_ARRAY_REVISION_1.

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

### -field FirstElementOffset

A USHORT value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_SWITCH_NIC_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

A ULONG value that specifies the number of <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a> elements that follow the <b>NDIS_SWITCH_NIC_ARRAY</b> structure.

### -field ElementSize

A ULONG value that specifies the size, in bytes, of the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a> elements that follows the <b>NDIS_SWITCH_NIC_ARRAY</b> structure.

## -remarks

The <b>NDIS_SWITCH_NIC_ARRAY</b> structure is returned in OID query requests of <a href="/windows-hardware/drivers/network/oid-switch-nic-array">OID_SWITCH_NIC_ARRAY</a>. An array of <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a> structures follows the <b>NDIS_SWITCH_NIC_ARRAY</b> structure in the information buffer that is associated with the OID query request. The <b>InformationBuffer</b> member of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

Extensible switch extensions can access individual <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a> structures inside an <b>NDIS_SWITCH_NIC_ARRAY</b> structure by using the <a href="/windows-hardware/drivers/network/ndis-switch-nic-at-array-index">NDIS_SWITCH_NIC_AT_ARRAY_INDEX</a> macro.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/network/ndis-switch-nic-at-array-index">NDIS_SWITCH_NIC_AT_ARRAY_INDEX</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_switch_nic_parameters">NDIS_SWITCH_NIC_PARAMETERS</a>



<a href="/windows-hardware/drivers/network/oid-switch-nic-array">OID_SWITCH_NIC_ARRAY</a>