---
UID: NS:ndis._NDIS_IF_PROVIDER_CHARACTERISTICS
title: _NDIS_IF_PROVIDER_CHARACTERISTICS (ndis.h)
description: The NDIS_IF_PROVIDER_CHARACTERISTICS structure defines NDIS network interface provider entry points and other provider characteristics.
old-location: netvista\ndis_if_provider_characteristics.htm
tech.root: netvista
ms.assetid: f295bea2-20d8-4c71-b78b-77d43840be2a
ms.date: 05/02/2018
keywords: ["_NDIS_IF_PROVIDER_CHARACTERISTICS structure"]
ms.keywords: "*PNDIS_IF_PROVIDER_CHARACTERISTICS, NDIS_IF_PROVIDER_CHARACTERISTICS, NDIS_IF_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_IF_PROVIDER_CHARACTERISTICS, PNDIS_IF_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_IF_PROVIDER_CHARACTERISTICS, ndis/NDIS_IF_PROVIDER_CHARACTERISTICS, ndis/PNDIS_IF_PROVIDER_CHARACTERISTICS, net_if_struct_ref_44fd781f-d830-4a18-86e9-b16eb3367d6a.xml, netvista.ndis_if_provider_characteristics"
f1_keywords:
 - "ndis/NDIS_IF_PROVIDER_CHARACTERISTICS"
 - "NDIS_IF_PROVIDER_CHARACTERISTICS"
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
- NDIS_IF_PROVIDER_CHARACTERISTICS
targetos: Windows
req.typenames: NDIS_IF_PROVIDER_CHARACTERISTICS, *PNDIS_IF_PROVIDER_CHARACTERISTICS
---

# _NDIS_IF_PROVIDER_CHARACTERISTICS structure


## -description


The NDIS_IF_PROVIDER_CHARACTERISTICS structure defines NDIS network interface provider entry points
  and other provider characteristics.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     interface provider characteristics structure (NDIS_IF_PROVIDER_CHARACTERISTICS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_OBJECT_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_IF_PROVIDER_CHARACTERISTICS_REVISION_1.


### -field QueryObjectHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-if_query_object">
     ProviderQueryObject</a> function.


### -field SetObjectHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-if_set_object">ProviderSetObject</a> function.


### -field Reserved1

Reserved for NDIS.


### -field Reserved2

Reserved for NDIS.


## -remarks



All NDIS network driver types can register as network interface providers. An NDIS interface provider
    initializes an NDIS_IF_PROVIDER_CHARACTERISTICS structure to define its provider entry points and other
    characteristics, if any.

To register as an interface provider, the driver passes a pointer to the initialized
    NDIS_IF_PROVIDER_CHARACTERISTICS structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterprovider">
    NdisIfRegisterProvider</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterprovider">NdisIfRegisterProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-if_query_object">ProviderQueryObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-if_set_object">ProviderSetObject</a>
 

 

