---
UID: NF:ndis.NdisAllocateSharedMemory
title: NdisAllocateSharedMemory function (ndis.h)
description: The NdisAllocateSharedMemory function allocates shared memory from a shared memory provider.
old-location: netvista\ndisallocatesharedmemory.htm
tech.root: netvista
ms.assetid: 1e4919df-7897-44c3-876f-0f1acfe6d5af
ms.date: 05/02/2018
keywords: ["NdisAllocateSharedMemory function"]
ms.keywords: NdisAllocateSharedMemory, NdisAllocateSharedMemory function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateSharedMemory, ndis_shared_memory_ref_252ce78e-6920-4825-9537-c1ddd2f9f900.xml, netvista.ndisallocatesharedmemory
f1_keywords:
 - "ndis/NdisAllocateSharedMemory"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisAllocateSharedMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateSharedMemory function


## -description


The 
  <b>NdisAllocateSharedMemory</b> function allocates shared memory from a shared memory provider.


## -parameters




### -param NdisHandle [in]

An NDIS driver or instance handle that was obtained during caller initialization. For example, a
     miniport driver can use the NDIS handle that it obtained from the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> or 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



### -param SharedMemoryParameters [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_parameters">
     NDIS_SHARED_MEMORY_PARAMETERS</a> structure that defines the requested attributes for the shared
     memory.


### -param pAllocationHandle [in, out]

A pointer to a location for a handle that identifies the shared memory that was allocated. The
     handle is available when the function returns or it is <b>NULL</b> if the function fails. The caller must use
     this handle to free the shared memory that was allocated successfully.


## -returns



<b>NdisAllocateSharedMemory</b> can return the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because there were insufficient resources to complete the operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of an invalid input parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The operation failed for unspecified reasons.

</td>
</tr>
</table>
 




## -remarks



<div class="alert"><b>Note</b>  A miniport driver must have already called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">NdisMRegisterScatterGatherDma</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a> to initialize a
  scatter/gather DMA channel before calling <b>NdisAllocateSharedMemory</b>.</div>
<div> </div>
NDIS drivers call the 
    <b>NdisAllocateSharedMemory</b> function to allocate a block of shared memory from an NDIS shared memory
    provider.

The 
    <i>SharedMemoryParameters</i> parameter contains a pointer to an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_parameters">
    NDIS_SHARED_MEMORY_PARAMETERS</a> structure that defines the requested attributes for the shared
    memory. If the <b>NDIS_SHARED_MEM_PARAMETERS_CONTIGUOUS</b> flag is not set in the 
    <b>Flags</b> member, shared memory can be specified in a scatter-gather list that is contained in
    non-contiguous memory.

NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-allocate_shared_memory_handler">NetAllocateSharedMemory</a> function of a shared memory provider from the context of the call to 
    <b>NdisAllocateSharedMemory</b>.

The driver must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreesharedmemory">NdisFreeSharedMemory</a> function to free
    the shared memory that it allocates with 
    <b>NdisAllocateSharedMemory</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_shared_memory_parameters">NDIS_SHARED_MEMORY_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreesharedmemory">NdisFreeSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-allocate_shared_memory_handler">NetAllocateSharedMemory</a>
 

 

