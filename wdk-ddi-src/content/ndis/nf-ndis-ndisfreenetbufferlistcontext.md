---
UID: NF:ndis.NdisFreeNetBufferListContext
title: NdisFreeNetBufferListContext function (ndis.h)
description: Call the NdisFreeNetBufferListContext function to release context space in the NET_BUFFER_LIST_CONTEXT structure of a NET_BUFFER_LIST structure.
old-location: netvista\ndisfreenetbufferlistcontext.htm
tech.root: netvista
ms.assetid: e5554790-a7a2-4c0d-a6ae-585ea909cd3d
ms.date: 05/02/2018
ms.keywords: NdisFreeNetBufferListContext, NdisFreeNetBufferListContext function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBufferListContext, ndis_netbuf_functions_ref_ee330dac-2453-46e7-a298-7d4a59caf0ab.xml, netvista.ndisfreenetbufferlistcontext
ms.topic: function
f1_keywords:
 - "ndis/NdisFreeNetBufferListContext"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
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
- NdisFreeNetBufferListContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeNetBufferListContext function


## -description


Call the 
  <b>NdisFreeNetBufferListContext</b> function to release context space in the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure of a
  
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.


## -parameters




### -param NetBufferList [in]

A pointer to a previously allocated NET_BUFFER_LIST structure.


### -param ContextSize [in]

The amount of context space to free.


## -returns



None




## -remarks



<b>NdisFreeNetBufferListContext</b> releases context space that was allocated in a previous call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatenetbufferlistcontext">
    NdisAllocateNetBufferListContext</a>. If 
    <b>NdisAllocateNetBufferListContext</b> allocated memory to satisfy in the call to 
    <b>NdisAllocateNetBufferListContext</b>, 
    <b>NdisFreeNetBufferListContext</b> frees the allocated memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatenetbufferlistcontext">
   NdisAllocateNetBufferListContext</a>
 

 

