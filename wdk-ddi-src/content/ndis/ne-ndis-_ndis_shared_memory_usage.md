---
UID: NE:ndis._NDIS_SHARED_MEMORY_USAGE
title: _NDIS_SHARED_MEMORY_USAGE (ndis.h)
description: The NDIS_SHARED_MEMORY_USAGE enumeration specifies how shared memory is used.
old-location: netvista\ndis_shared_memory_usage.htm
tech.root: netvista
ms.assetid: c46102dd-26ea-459b-8cc2-f7e2d2e2f2ad
ms.date: 05/02/2018
keywords: ["_NDIS_SHARED_MEMORY_USAGE enumeration"]
ms.keywords: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE enumeration [Network Drivers Starting with Windows Vista], NdisSharedMemoryUsageMax, NdisSharedMemoryUsageOther, NdisSharedMemoryUsageReceive, NdisSharedMemoryUsageReceiveData, NdisSharedMemoryUsageReceiveHeader, NdisSharedMemoryUsageReceiveLookahead, NdisSharedMemoryUsageReceivePostLookahead, NdisSharedMemoryUsageUndefined, NdisSharedMemoryUsageXmit, NdisSharedMemoryUsageXmitData, NdisSharedMemoryUsageXmitHeader, PNDIS_SHARED_MEMORY_USAGE, PNDIS_SHARED_MEMORY_USAGE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SHARED_MEMORY_USAGE, ndis/NDIS_SHARED_MEMORY_USAGE, ndis/NdisSharedMemoryUsageMax, ndis/NdisSharedMemoryUsageOther, ndis/NdisSharedMemoryUsageReceive, ndis/NdisSharedMemoryUsageReceiveData, ndis/NdisSharedMemoryUsageReceiveHeader, ndis/NdisSharedMemoryUsageReceiveLookahead, ndis/NdisSharedMemoryUsageReceivePostLookahead, ndis/NdisSharedMemoryUsageUndefined, ndis/NdisSharedMemoryUsageXmit, ndis/NdisSharedMemoryUsageXmitData, ndis/NdisSharedMemoryUsageXmitHeader, ndis/PNDIS_SHARED_MEMORY_USAGE, ndis_shared_memory_ref_fc268c92-4745-4916-8aab-e1e67e12d217.xml, netvista.ndis_shared_memory_usage"
f1_keywords:
 - "ndis/NDIS_SHARED_MEMORY_USAGE"
 - "NDIS_SHARED_MEMORY_USAGE"
req.header: ndis.h
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
- ndis.h
api_name:
- NDIS_SHARED_MEMORY_USAGE
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# _NDIS_SHARED_MEMORY_USAGE enumeration


## -description


The NDIS_SHARED_MEMORY_USAGE enumeration specifies how shared memory is used.


## -enum-fields




### -field NdisSharedMemoryUsageUndefined

The shared memory application is not defined.


### -field NdisSharedMemoryUsageXmit

The shared memory contains transmit data buffers.


### -field NdisSharedMemoryUsageXmitHeader

The shared memory contains transmit header buffers.


### -field NdisSharedMemoryUsageXmitData

The shared memory contains transmit data.


### -field NdisSharedMemoryUsageReceive

The shared memory contains receive data buffers.


### -field NdisSharedMemoryUsageReceiveLookahead

The shared memory contains receive lookahead buffers.


### -field NdisSharedMemoryUsageReceivePostLookahead

The shared memory contains received post lookahead information.


### -field NdisSharedMemoryUsageReceiveHeader

The shared memory contains receive header information.


### -field NdisSharedMemoryUsageReceiveData

The shared memory contains receive data.


### -field NdisSharedMemoryUsageOther

The shared memory application is not specified.


### -field NdisSharedMemoryUsageMax

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The NDIS_SHARED_MEMORY_USAGE enumeration is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_parameters">
    NDIS_SHARED_MEMORY_PARAMETERS</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_scatter_gather_list_parameters">
    NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_scatter_gather_list_parameters">
   NDIS_SCATTER_GATHER_LIST_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_parameters">NDIS_SHARED_MEMORY_PARAMETERS</a>
 

 

