---
UID: NS:ntddndis._NDIS_ROUTING_DOMAIN_ENTRY
title: _NDIS_ROUTING_DOMAIN_ENTRY (ntddndis.h)
description: The NDIS_ROUTING_DOMAIN_ENTRY structure is used by the OID_GEN_ISOLATION_PARAMETERS OID to return the routing domain entries for a VM network adapter's port.
old-location: netvista\ndis_routing_domain_entry.htm
tech.root: netvista
ms.assetid: 65E39285-AFD2-4098-A983-C7FA06505407
ms.date: 05/02/2018
ms.keywords: "*PNDIS_ROUTING_DOMAIN_ENTRY, NDIS_ROUTING_DOMAIN_ENTRY, NDIS_ROUTING_DOMAIN_ENTRY structure [Network Drivers Starting with Windows Vista], PNDIS_ROUTING_DOMAIN_ENTRY, PNDIS_ROUTING_DOMAIN_ENTRY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_ROUTING_DOMAIN_ENTRY, netvista.ndis_routing_domain_entry, ntddndis/NDIS_ROUTING_DOMAIN_ENTRY, ntddndis/PNDIS_ROUTING_DOMAIN_ENTRY"
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_ROUTING_DOMAIN_ENTRY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_ROUTING_DOMAIN_ENTRY
product:
- Windows
targetos: Windows
req.typenames: NDIS_ROUTING_DOMAIN_ENTRY, *PNDIS_ROUTING_DOMAIN_ENTRY
---

# _NDIS_ROUTING_DOMAIN_ENTRY structure


## -description


The <b>NDIS_ROUTING_DOMAIN_ENTRY</b> structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-isolation-parameters">OID_GEN_ISOLATION_PARAMETERS</a> OID to return the routing domain entries for a VM network adapter's port.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_ROUTING_DOMAIN_ENTRY</b>  structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. To specify the version of the <b>NDIS_ROUTING_DOMAIN_ENTRY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_ROUTING_DOMAIN_ENTRY_REVISION_1

Original version for NDIS 6.40 and later.

Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_ROUTING_DOMAIN_ENTRY_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field RoutingDomainId

The routing domain identifier for the VM network adapter. This identifier is  a GUID.


### -field RoutingDomainName

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_isolation_name">NDIS_ISOLATION_NAME</a> structure that contains the routing domain name for the VM network adapter.


### -field NumIsolationEntries

A <b>ULONG</b> value that specifies the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_isolation_entry">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a> structures in the array that follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_isolation_parameters">NDIS_ISOLATION_PARAMETERS</a> structure.


### -field FirstIsolationEntryOffset

A <b>ULONG</b> value that specifies the offset, in bytes, to the first <b>NDIS_ROUTING_DOMAIN_ENTRY</b> element in the array that follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_isolation_parameters">NDIS_ISOLATION_PARAMETERS</a> structure in the buffer that the <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure points to. The offset is measured from the start of the <b>NDIS_ROUTING_DOMAIN_ENTRY</b> structure to the beginning of the first element of the array.

<div class="alert"><b>Note</b>  If the value of <b>NumRoutingDomainEntries</b> is zero, this member is ignored.</div>
<div> </div>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_isolation_parameters">NDIS_ISOLATION_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-routing-domain-entry-get-next">NDIS_ROUTING_DOMAIN_ENTRY_GET_NEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_routing_domain_isolation_entry">NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-isolation-parameters">OID_GEN_ISOLATION_PARAMETERS</a>
 

 

