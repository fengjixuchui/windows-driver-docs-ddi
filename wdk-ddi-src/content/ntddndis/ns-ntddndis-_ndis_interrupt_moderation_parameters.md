---
UID: NS:ntddndis._NDIS_INTERRUPT_MODERATION_PARAMETERS
title: _NDIS_INTERRUPT_MODERATION_PARAMETERS (ntddndis.h)
description: The NDIS_INTERRUPT_MODERATION_PARAMETERS structure defines interrupt parameters for the OID_GEN_INTERRUPT_MODERATION OID.
old-location: netvista\ndis_interrupt_moderation_parameters.htm
tech.root: netvista
ms.assetid: e2270dbc-0bc3-4bef-9e11-26006d8f0d71
ms.date: 05/02/2018
keywords: ["NDIS_INTERRUPT_MODERATION_PARAMETERS structure"]
ms.keywords: "*PNDIS_INTERRUPT_MODERATION_PARAMETERS, NDIS_INTERRUPT_MODERATION_PARAMETERS, NDIS_INTERRUPT_MODERATION_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_INTERRUPT_MODERATION_PARAMETERS, PNDIS_INTERRUPT_MODERATION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_INTERRUPT_MODERATION_PARAMETERS, netvista.ndis_interrupt_moderation_parameters, ntddndis/NDIS_INTERRUPT_MODERATION_PARAMETERS, ntddndis/PNDIS_INTERRUPT_MODERATION_PARAMETERS, oid_structures_ref_448cef08-e024-4e5b-a370-fb6e8d78c9cd.xml"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: NDIS_INTERRUPT_MODERATION_PARAMETERS, *PNDIS_INTERRUPT_MODERATION_PARAMETERS
f1_keywords:
 - _NDIS_INTERRUPT_MODERATION_PARAMETERS
 - ntddndis/_NDIS_INTERRUPT_MODERATION_PARAMETERS
 - PNDIS_INTERRUPT_MODERATION_PARAMETERS
 - ntddndis/PNDIS_INTERRUPT_MODERATION_PARAMETERS
 - NDIS_INTERRUPT_MODERATION_PARAMETERS
 - ntddndis/NDIS_INTERRUPT_MODERATION_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_INTERRUPT_MODERATION_PARAMETERS
---

# _NDIS_INTERRUPT_MODERATION_PARAMETERS structure


## -description

The NDIS_INTERRUPT_MODERATION_PARAMETERS structure defines interrupt parameters for the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-interrupt-moderation">OID_GEN_INTERRUPT_MODERATION</a> OID.

## -struct-fields

### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_INTERRUPT_MODERATION_PARAMETERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_INTERRUPT_MODERATION_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_INTERRUPT_MODERATION_PARAMETERS_REVISION_1.

### -field Flags

A bitwise OR of the following flags:
     





#### NDIS_INTERRUPT_MODERATION_CHANGE_NEEDS_RESET

A network interface card (NIC) must have a hardware reset to enable or disable interrupt
       moderation.



#### NDIS_INTERRUPT_MODERATION_CHANGE_NEEDS_REINITIALIZE

A miniport driver must complete a halt and reinitialize cycle to enable or disable interrupt
       moderation. If this flag is enabled, there is also a hardware reset.

### -field InterruptModeration

An NDIS_INTERRUPT_MODERATION-typed value that indicates or specifies the current interrupt
     moderation status.
     

The following values are supported:





#### NdisInterruptModerationUnknown

In an OID query, this value indicates that the miniport driver cannot determine whether
       interrupt moderation is enabled or disabled on a NIC. This value is invalid for a set request.



#### NdisInterruptModerationNotSupported

In an OID query, this value indicates that the NIC or its miniport driver does not support
       interrupt moderation. This value is invalid for a set request.



#### NdisInterruptModerationEnabled

In an OID query, this value indicates that interrupt moderation is enabled on the NIC. In an OID
       set, 
       <b>NdisInterruptModerationEnabled</b> indicates that interrupt moderation should be enabled on the
       NIC.



#### NdisInterruptModerationDisabled

In an OID query, this value indicates that interrupt moderation is disabled on the NIC. In an
       OID set, 
       <b>NdisInterruptModerationDisabled</b> indicates that interrupt moderation should be disabled on the
       NIC.

## -remarks

The NDIS_INTERRUPT_MODERATION_PARAMETERS structure defines interrupt parameters for the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-interrupt-moderation">OID_GEN_INTERRUPT_MODERATION</a> OID
    query and set operations. Only the 
    <b>NdisInterruptModerationEnabled</b> and 
    <b>NdisInterruptModerationDisabled</b> values for the 
    <b>InterruptModeration</b> member apply to set operations.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-interrupt-moderation">OID_GEN_INTERRUPT_MODERATION</a>

