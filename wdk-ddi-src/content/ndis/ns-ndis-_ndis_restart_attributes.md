---
UID: NS:ndis._NDIS_RESTART_ATTRIBUTES
title: _NDIS_RESTART_ATTRIBUTES (ndis.h)
description: The NDIS_RESTART_ATTRIBUTES structure identifies an attributes entry in a linked list of restart attributes.
old-location: netvista\ndis_restart_attributes.htm
tech.root: netvista
ms.assetid: 1f9f4b91-bd1f-4daa-ac98-6372bf55c2ab
ms.date: 05/02/2018
keywords: ["_NDIS_RESTART_ATTRIBUTES structure"]
ms.keywords: "*PNDIS_RESTART_ATTRIBUTES, NDIS_RESTART_ATTRIBUTES, NDIS_RESTART_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_RESTART_ATTRIBUTES, PNDIS_RESTART_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RESTART_ATTRIBUTES, miniport_structures_ref_64cf43cc-1d89-4de3-9e8e-77d590d44d3c.xml, ndis/NDIS_RESTART_ATTRIBUTES, ndis/PNDIS_RESTART_ATTRIBUTES, netvista.ndis_restart_attributes"
f1_keywords:
 - "ndis/NDIS_RESTART_ATTRIBUTES"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- ndis.h
api_name:
- NDIS_RESTART_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: NDIS_RESTART_ATTRIBUTES, *PNDIS_RESTART_ATTRIBUTES
---

# _NDIS_RESTART_ATTRIBUTES structure


## -description


The NDIS_RESTART_ATTRIBUTES structure identifies an attributes entry in a linked list of restart
  attributes.


## -struct-fields




### -field Next

A pointer to an NDIS_RESTART_ATTRIBUTES structure that you can use to access the next set of
     restart attributes in the linked list of attributes. If there are no additional attributes, this member
     is <b>NULL</b>.


### -field Oid

The NDIS object identifier for the information that is in the 
     <b>Data</b> member. For example, if 
     <b>Oid</b> is 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-miniport-restart-attributes">
     OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>, the 
     <b>Data</b> member contains an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_general_attributes">
     NDIS_RESTART_GENERAL_ATTRIBUTES</a> structure.


### -field DataLength

The length, in bytes, of the information that is stored in the 
     <b>Data</b> member.


### -field Data

A buffer that contains the information that is associated with the OID that is specified in the 
     <b>Oid</b> member.


## -remarks



When NDIS restarts a driver stack, NDIS passes a pointer to a linked list of restart attributes to
    miniport, filter, and protocol drivers.

When it calls a miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a> function, NDIS passes a
    pointer to an NDIS_RESTART_ATTRIBUTES structure to the miniport driver in the 
    <b>RestartAttributes</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_restart_parameters">
    NDIS_MINIPORT_RESTART_PARAMETERS</a> structure.

When it calls a filter driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_restart">FilterRestart</a> function, NDIS passes a
    pointer to an NDIS_RESTART_ATTRIBUTES structure to the filter driver in the 
    <b>RestartAttributes</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_restart_parameters">
    NDIS_FILTER_RESTART_PARAMETERS</a> structure.

When it restarts a protocol binding, NDIS provides a pointer to an NDIS_RESTART_ATTRIBUTES structure
    in the 
    <b>RestartAttributes</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_restart_parameters">
    NDIS_PROTOCOL_RESTART_PARAMETERS</a> structure. To restart a protocol binding, NDIS calls a protocol
    driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function. The 
    <b>NetPnPEvent</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">
    NET_PNP_EVENT_NOTIFICATION</a> structure, that NDIS passes to 
    <i>ProtocolNetPnPEvent</i>, contains a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event">NET_PNP_EVENT</a> structure. The NET_PNP_EVENT
    structure specifies 
    <b>NetEventRestart</b> in the 
    <b>NetEvent</b> member and a pointer to the NDIS_PROTOCOL_RESTART_PARAMETERS structure in the 
    <b>Buffer</b> member.

If the restart attributes pointer that NDIS passes to NDIS drivers is <b>NULL</b>, the drivers should not
    propagate their attributes changes up the driver stack. In this situation, drivers should not modify, or
    report any attributes changes.

If the restart attributes pointer is not <b>NULL</b>, the linked list of NDIS_RESTART_ATTRIBUTES structures
    has at least one entry that contains an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_general_attributes">
    NDIS_RESTART_GENERAL_ATTRIBUTES</a> structure. The rest of the entries, if any, contain media-specific
    attributes.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_restart">FilterRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_restart_parameters">
   NDIS_FILTER_RESTART_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_restart_parameters">
   NDIS_MINIPORT_RESTART_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_protocol_restart_parameters">
   NDIS_PROTOCOL_RESTART_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_restart_general_attributes">
   NDIS_RESTART_GENERAL_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">NET_PNP_EVENT_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-miniport-restart-attributes">
   OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>
 

 

