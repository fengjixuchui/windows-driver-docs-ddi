---
UID: NF:ndis.NdisAllocateMdl
title: NdisAllocateMdl function (ndis.h)
description: The NdisAllocateMdl function allocates an MDL that describes the memory buffer at the specified virtual address.
old-location: netvista\ndisallocatemdl.htm
tech.root: netvista
ms.assetid: 4863fe31-2c89-47af-99ed-02055e67621d
ms.date: 05/02/2018
ms.keywords: NdisAllocateMdl, NdisAllocateMdl function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateMdl, ndis_netbuf_functions_ref_73b9ab32-14a8-4441-a057-c6fe91ddfb43.xml, netvista.ndisallocatemdl
ms.topic: function
f1_keywords:
 - "ndis/NdisAllocateMdl"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateMdl
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisAllocateMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateMdl function


## -description


The 
  <b>NdisAllocateMdl</b> function allocates an MDL that describes the memory buffer at the specified virtual
  address.


## -parameters




### -param NdisHandle [in]

An NDIS handle that was obtained during caller initialization. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/obtaining-pool-handles">Obtaining Pool Handles</a>.


### -param VirtualAddress [in]

A pointer to the base virtual address of the buffer that the MDL is to describe.

<div class="alert"><b>Important</b>  <p class="note">The <b>VirtualAddress</b> parameter for <b>NdisAllocateMdl</b> only accepts memory from the nonpaged pool. In other words, it requires memory from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exallocatepool">ExAllocatePool</a>*(NonPagedNx), <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatememorywithtagpriority">NdisAllocateMemoryWithTagPriority</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatesharedmemory">NdisMAllocateSharedMemory</a>. In particular, it should <b>not</b> be used with memory from the stack, paged pool, driver global data, or other memory regions.

<p class="note">If a driver needs to build an MDL for one of these non-nonpaged pool regions, it should use the appropriate kernel APIs for that type of memory, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a> combined with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages.</a>


</div>
<div> </div>

### -param Length [in]

The size, in bytes, of the memory buffer.


## -returns



<b>NdisAllocateMdl</b> returns a pointer to the allocated MDL. If the allocation fails, the return value
     is <b>NULL</b>.




## -remarks



All MDLs that are allocated by calling 
    <b>NdisAllocateMdl</b> must be freed by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfreemdl">NdisFreeMdl</a> function.

<b>NdisAllocateMdl</b> allocates memory and builds the MDL in one step. This process is different from 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>, which only allocates memory for
    the MDL, meaning the caller must build the MDL by calling either 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages.</a>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exallocatepool">ExAllocatePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatememorywithtagpriority">NdisAllocateMemoryWithTagPriority</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfreemdl">NdisFreeMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatesharedmemory">NdisMAllocateSharedMemory</a>
 

 

