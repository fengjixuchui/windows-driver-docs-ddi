---
UID: NS:ndis._IPSEC_OFFLOAD_V2_UPDATE_SA
title: _IPSEC_OFFLOAD_V2_UPDATE_SA (ndis.h)
description: The IPSEC_OFFLOAD_V2_UPDATE_SA structure updates information about security associations (SAs) that a miniport driver previously added to a NIC and a pointer to the next IPSEC_OFFLOAD_V2_UPDATE_SA structure in a linked list.
old-location: netvista\ipsec_offload_v2_update_sa.htm
tech.root: netvista
ms.assetid: d9fe5fec-75e3-4ea6-a4ac-16756fa8dc38
ms.date: 05/02/2018
keywords: ["IPSEC_OFFLOAD_V2_UPDATE_SA structure"]
ms.keywords: "*PIPSEC_OFFLOAD_V2_UPDATE_SA, IPSEC_OFFLOAD_V2_UPDATE_SA, IPSEC_OFFLOAD_V2_UPDATE_SA structure [Network Drivers Starting with Windows Vista], PIPSEC_OFFLOAD_V2_UPDATE_SA, PIPSEC_OFFLOAD_V2_UPDATE_SA structure pointer [Network Drivers Starting with Windows Vista], _IPSEC_OFFLOAD_V2_UPDATE_SA, ndis/IPSEC_OFFLOAD_V2_UPDATE_SA, ndis/PIPSEC_OFFLOAD_V2_UPDATE_SA, netvista.ipsec_offload_v2_update_sa, task_offload_IPsecv2_ref_2a34fbb7-fa5d-49f3-844c-c5e8df229a54.xml"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
req.typenames: IPSEC_OFFLOAD_V2_UPDATE_SA, *PIPSEC_OFFLOAD_V2_UPDATE_SA
f1_keywords:
 - _IPSEC_OFFLOAD_V2_UPDATE_SA
 - ndis/_IPSEC_OFFLOAD_V2_UPDATE_SA
 - PIPSEC_OFFLOAD_V2_UPDATE_SA
 - ndis/PIPSEC_OFFLOAD_V2_UPDATE_SA
 - IPSEC_OFFLOAD_V2_UPDATE_SA
 - ndis/IPSEC_OFFLOAD_V2_UPDATE_SA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - IPSEC_OFFLOAD_V2_UPDATE_SA
---

# _IPSEC_OFFLOAD_V2_UPDATE_SA structure


## -description

<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The IPSEC_OFFLOAD_V2_UPDATE_SA structure updates information about security associations (SAs) that a
  miniport driver previously added to a NIC and a pointer to the next IPSEC_OFFLOAD_V2_UPDATE_SA structure in
  a linked list.

## -struct-fields

### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     IPSEC_OFFLOAD_V2_UPDATE_SA structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_IPSEC_OFFLOAD_V2_UPDATE_SA_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_IPSEC_OFFLOAD_V2_UPDATE_SA_REVISION_1.

### -field OffloadHandle

An NDIS handle that identifies the SA. The miniport driver provided this handle in response to an 
     OID set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>.

### -field Operation

The IPsec operation for which the SA is to be used. The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ipsec_offload_v2_operation">
     IPSEC_OFFLOAD_V2_OPERATION</a> enumeration defines the supported operations.

### -field Spi

A 32 bit security parameters index (SPI) for the SA.

### -field SequenceNumberHighOrder

The high-order bit of an IPsec sequence number. This bit is not included in the IPsec
     header.

## -remarks

The IPSEC_OFFLOAD_V2_UPDATE_SA structure specifies updates for a SA and a pointer to the next
    IPSEC_OFFLOAD_V2_UPDATE_SA structure in a linked list. The IPSEC_OFFLOAD_V2_UPDATE_SA structure is used
    with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-update-sa">
    OID_TCP_TASK_IPSEC_OFFLOAD_V2_UPDATE_SA</a> OID.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-_ipsec_offload_v2_operation">IPSEC_OFFLOAD_V2_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-update-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_UPDATE_SA</a>

