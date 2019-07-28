---
UID: NC:ndischimney.W_INITIATE_OFFLOAD_HANDLER
title: W_INITIATE_OFFLOAD_HANDLER (ndischimney.h)
description: MiniportInitiateOffload offloads TCP chimney state from the host stack.
old-location: netvista\miniportinitiateoffload.htm
tech.root: netvista
ms.assetid: f430642b-01bf-4ed7-bfea-e8dd8d5a8208
ms.date: 05/02/2018
ms.keywords: MiniportInitiateOffload, MiniportInitiateOffload callback function [Network Drivers Starting with Windows Vista], W_INITIATE_OFFLOAD_HANDLER, W_INITIATE_OFFLOAD_HANDLER callback, ndischimney/MiniportInitiateOffload, netvista.miniportinitiateoffload, tcp_chim_miniport_func_58c338e0-ea8e-41c2-a781-a32f4be7758c.xml
ms.topic: callback
f1_keywords:
 - "ndischimney/MiniportInitiateOffload"
req.header: ndischimney.h
req.include-header: Ndischimney.h
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndischimney.h
api_name:
- MiniportInitiateOffload
product:
- Windows
targetos: Windows
req.typenames: 
---

# W_INITIATE_OFFLOAD_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

<i>MiniportInitiateOffload</i> offloads TCP chimney state from the host stack.


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The miniport driver provided this handle to NDIS when it
     called 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsetminiportattributes">
     NdisMSetMiniportAttributes</a> from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param OffloadBlockList [in, out]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures.


## -returns



None




## -remarks



The 
    <i>MiniportInitiateOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the offload
    operation asynchronously by calling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndisminitiateoffloadcomplete">
    NdisMInitiateOffloadComplete</a>. The state tree pointed to by the 
    <i>OffloadBlockList</i> pointer is valid until the miniport driver calls 
    <b>NdisMInitiateOffloadComplete</b>.

After returning from its 
    <i>MiniportInitiateOffload</i> function, the offload target offloads state from the state tree. An
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure whose 
    <b>MiniportOffloadContext</b> member points to a memory location that contains a <b>NULL</b> value is followed by
    state to be offloaded. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/storing-and-referencing-offloaded-state">Storing and Referencing
    Offloaded State</a>. The 
    <b>Header</b> member of an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure contains a 
    <b>Type</b> member that specifies the type of offload state, and by implication, the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">offload state structure</a> or structures,
    that immediately follow the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in memory.

The offload target offloads the offload state associated with an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure into an offload context area. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/storing-and-referencing-offloaded-state">Storing and Referencing
    Offloaded State</a>.

When offloading state, the offload target must traverse the state tree in 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/traversing-a-state-tree">depth-first/breadth-next fashion</a>. It
    is critical that an offload target offloads state in this way.

Some of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in the state tree that are passed to the 
    <i>MiniportInitiateOffload</i> function can be placeholders or linking nodes that do not have accompanying
    state to be offloaded. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/placeholders--linkers--and-new-offloads">Placeholders, Linkers, and
    New Offloads</a>.

The offload target can receive buffered data from the host stack for a connection that is being
    offloaded. The offload target must copy this data into its own buffer before completing the offload
    operation. For more information about processing buffered receive data, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/handling-buffered-receive-data-during-and-after-an-offload-operation">
    Handling Buffered Receive Data During and After an Offload Operation</a>.

For each state object that it offloads, the offload target must also supply a PVOID value that
    references the offload context area in which the offload target stores the state object. The offload
    target writes this PVOID value to the memory location pointed to by the 
    <b>*MiniportOffloadContext</b> member of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure associated with
    the state. If the offload target did not successfully offload the state associated with the
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure, it should not write a value to the memory location pointed to
    by the 
    <b>*MiniportOffloadContext</b> member. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/storing-and-referencing-offloaded-state">Storing and Referencing
    Offloaded State</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nf-ndischimney-ndisminitiateoffloadcomplete">NdisMInitiateOffloadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
 

 

