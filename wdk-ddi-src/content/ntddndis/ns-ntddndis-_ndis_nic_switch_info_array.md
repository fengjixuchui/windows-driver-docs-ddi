---
UID: NS:ntddndis._NDIS_NIC_SWITCH_INFO_ARRAY
title: _NDIS_NIC_SWITCH_INFO_ARRAY (ntddndis.h)
description: The NDIS_NIC_SWITCH_INFO_ARRAY structure specifies an array. Each element in the array specifies the attributes of a network adapter switch that has been created on the network adapter.
old-location: netvista\ndis_nic_switch_info_array.htm
tech.root: netvista
ms.assetid: bff2b133-bbef-4f2a-a7b1-34d7cf364205
ms.date: 05/02/2018
keywords: ["NDIS_NIC_SWITCH_INFO_ARRAY structure"]
ms.keywords: "*PNDIS_NIC_SWITCH_INFO_ARRAY, NDIS_NIC_SWITCH_INFO_ARRAY, NDIS_NIC_SWITCH_INFO_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_INFO_ARRAY, PNDIS_NIC_SWITCH_INFO_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_INFO_ARRAY, netvista.ndis_nic_switch_info_array, ntddndis/NDIS_NIC_SWITCH_INFO_ARRAY, ntddndis/PNDIS_NIC_SWITCH_INFO_ARRAY"
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
req.typenames: NDIS_NIC_SWITCH_INFO_ARRAY, *PNDIS_NIC_SWITCH_INFO_ARRAY
f1_keywords:
 - _NDIS_NIC_SWITCH_INFO_ARRAY
 - ntddndis/_NDIS_NIC_SWITCH_INFO_ARRAY
 - PNDIS_NIC_SWITCH_INFO_ARRAY
 - ntddndis/PNDIS_NIC_SWITCH_INFO_ARRAY
 - NDIS_NIC_SWITCH_INFO_ARRAY
 - ntddndis/NDIS_NIC_SWITCH_INFO_ARRAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_NIC_SWITCH_INFO_ARRAY
---

# _NDIS_NIC_SWITCH_INFO_ARRAY structure


## -description

The <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure specifies an array. Each element in the array specifies the attributes  of a network adapter switch that has been created on the network adapter.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

NDIS sets the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure, NDIS sets the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_INFO_ARRAY_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_INFO_ARRAY_REVISION_1.

### -field FirstElementOffset

A ULONG value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_info">NDIS_NIC_SWITCH_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

A ULONG value that specifies the number of elements that follow the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure.

### -field ElementSize

A ULONG value that specifies the size, in bytes, of each element that follows the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure.

## -remarks

NDIS returns an <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure in the following ways:

<ul>
<li>
When NDIS handles an OID query request of <a href="/windows-hardware/drivers/network/oid-nic-switch-enum-switches">OID_NIC_SWITCH_ENUM_SWITCHES</a>, it returns a pointer to an <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure in the <b>InformationBuffer</b> member of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>.

</li>
<li>When NDIS calls the <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>
function, NDIS passes a pointer to an <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure in the <i>BindParameters</i> parameter. NDIS sets the  <b>NicSwitchArray</b> member of the <b>NDIS_BIND_PARAMETERS</b> structure to a pointer to an <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure. </li>
<li>When NDIS calls the <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>
function, NDIS passes a pointer to an <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a> structure in the <i>AttachParameters</i> parameter. NDIS sets the  <b>NicSwitchArray</b> member of the <b>NDIS_FILTER_ATTACH_PARAMETERS</b> structure to a pointer to an <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure.</li>
</ul>
Each
    element in the array that follows the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure is an     
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_info">NDIS_NIC_SWITCH_INFO</a> structure.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, only the <b>NDIS_NIC_SWITCH_INFO</b> that describes the information about the default network adapter switch is returned through an OID query request of <a href="/windows-hardware/drivers/network/oid-nic-switch-enum-switches">OID_NIC_SWITCH_ENUM_SWITCHES</a>.</div>
<div> </div>

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_info">NDIS_NIC_SWITCH_INFO</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-enum-switches">OID_NIC_SWITCH_ENUM_SWITCHES</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>