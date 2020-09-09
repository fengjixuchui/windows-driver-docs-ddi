---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
title: _NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN (ntddndis.h)
description: The NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure is used to specify the routing domain properties of a VM network adapter.
old-location: netvista\ndis_switch_port_property_routing_domain.htm
tech.root: netvista
ms.assetid: 6E1DF4F3-9ED4-4E34-A768-1B5008D61B0C
ms.date: 05/02/2018
keywords: ["NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure"]
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, netvista.ndis_switch_port_property_routing_domain, ntddndis/NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
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
req.typenames: NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN, *PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
f1_keywords:
 - _NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
 - ntddndis/_NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
 - PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
 - ntddndis/PNDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
 - NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
 - ntddndis/NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN
---

# _NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN structure


## -description

The <b>NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</b> structure is used to specify the routing domain properties of a VM network adapter.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</b>  structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_REVISION_1

Original version for NDIS 6.40 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN_REVISION_1</b>.

### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

### -field RoutingDomainId

The routing domain identifier for the VM network adapter. This identifier is a GUID.

### -field RoutingDomainName

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_isolation_name">NDIS_ISOLATION_NAME</a> structure that contains the routing domain name for the VM network adapter.

### -field NumIsolationEntries

A <b>ULONG</b> value that specifies the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_isolation_entry">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a> in the array that follows the <b>NDIS_SWITCH_PORT_PROPERTY_ROUTING_DOMAIN</b> structure.



#### FirstIsolationEntryOffset

The offset, in bytes, from the beginning of the buffer pointed to by the <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure to the first isolation entry.

### -field FirstIsolationEntryOffset

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_isolation_name">NDIS_ISOLATION_NAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_entry">NDIS_ROUTING_DOMAIN_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_isolation_entry">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-property-parameters-get-property">NDIS_SWITCH_PROPERTY_PARAMETERS_GET_PROPERTY</a>

