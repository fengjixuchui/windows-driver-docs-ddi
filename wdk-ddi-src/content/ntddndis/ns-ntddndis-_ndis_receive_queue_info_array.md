---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_INFO_ARRAY
title: _NDIS_RECEIVE_QUEUE_INFO_ARRAY (ntddndis.h)
description: The NDIS_RECEIVE_QUEUE_INFO_ARRAY structure specifies a list of receive queues on a network adapter.
old-location: netvista\ndis_receive_queue_info_array.htm
tech.root: netvista
ms.assetid: 6a026c2b-e2ed-41bf-9482-0fdc64b175f2
ms.date: 05/02/2018
keywords: ["_NDIS_RECEIVE_QUEUE_INFO_ARRAY structure"]
ms.keywords: "*PNDIS_RECEIVE_QUEUE_INFO_ARRAY, NDIS_RECEIVE_QUEUE_INFO_ARRAY, NDIS_RECEIVE_QUEUE_INFO_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_INFO_ARRAY, PNDIS_RECEIVE_QUEUE_INFO_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_INFO_ARRAY, netvista.ndis_receive_queue_info_array, ntddndis/NDIS_RECEIVE_QUEUE_INFO_ARRAY, ntddndis/PNDIS_RECEIVE_QUEUE_INFO_ARRAY, virtual_machine_queue_ref_126f14fb-44b8-47bc-bc0d-eaa435470a6c.xml"
f1_keywords:
 - "ntddndis/NDIS_RECEIVE_QUEUE_INFO_ARRAY"
 - "NDIS_RECEIVE_QUEUE_INFO_ARRAY"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- NDIS_RECEIVE_QUEUE_INFO_ARRAY
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_INFO_ARRAY, *PNDIS_RECEIVE_QUEUE_INFO_ARRAY
---

# _NDIS_RECEIVE_QUEUE_INFO_ARRAY structure


## -description


The <b>NDIS_RECEIVE_QUEUE_INFO_ARRAY</b> structure specifies a list of receive queues on a network adapter.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_QUEUE_INFO_ARRAY</b>  structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_QUEUE_INFO_ARRAY_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_INFO_ARRAY_REVISION_1</b>.


### -field FirstElementOffset

A ULONG value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_RECEIVE_QUEUE_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_info">
     NDIS_RECEIVE_QUEUE_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

A <b>ULONG</b> value that represents the number of elements in the list of elements that follow the
     <b>NDIS_RECEIVE_QUEUE_INFO_ARRAY</b> structure.


### -field ElementSize

A <b>ULONG</b> value that specifies the size, in bytes, of each element in the array.


## -remarks



The <b>NDIS_RECEIVE_QUEUE_INFO_ARRAY</b> structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-enum-queues">
    OID_RECEIVE_FILTER_ENUM_QUEUES</a> OID that enumerates receive queues on a network adapter. Each
    element in the array is an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_info">
    NDIS_RECEIVE_QUEUE_INFO</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_receive_queue_info">NDIS_RECEIVE_QUEUE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-enum-queues">OID_RECEIVE_FILTER_ENUM_QUEUES</a>
 

 

