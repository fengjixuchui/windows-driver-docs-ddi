---
UID: NF:ndischimney.NdisMInvalidateOffloadComplete
title: NdisMInvalidateOffloadComplete function (ndischimney.h)
description: An offload target calls the NdisMInvalidateOffloadComplete function to complete an invalidate offload operation that was initiated by a previous call to the MiniportInvalidateOffload function of the offload target.
old-location: netvista\ndisminvalidateoffloadcomplete.htm
tech.root: netvista
ms.assetid: fd14e983-ea4b-41f2-973d-88b114306e75
ms.date: 05/02/2018
ms.keywords: NdisMInvalidateOffloadComplete, NdisMInvalidateOffloadComplete function [Network Drivers Starting with Windows Vista], ndischimney/NdisMInvalidateOffloadComplete, netvista.ndisminvalidateoffloadcomplete, tcp_chim_ndis_func_14e16158-2af9-4901-a986-0bfa329d9ac5.xml
ms.topic: function
f1_keywords:
 - "ndischimney/NdisMInvalidateOffloadComplete"
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
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
- HeaderDef
api_location:
- ndischimney.h
api_name:
- NdisMInvalidateOffloadComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMInvalidateOffloadComplete function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMInvalidateOffloadComplete</b> function to complete an invalidate offload operation that was
  initiated by a previous call to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_invalidate_offload_handler">
  MiniportInvalidateOffload</a> function of the offload target.


## -parameters




### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. The ofload target obtained this pointer as an input
     parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_invalidate_offload_handler">
     MiniportInvalidateOffload</a> function.


## -returns



None




## -remarks



Before calling the 
    <b>NdisMInvalidateOffloadComplete</b> function, the offload target must write either of the following
    NDIS_STATUS values to the 
    <b>Status</b> member of each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree:

<ul>
<li>
NDIS_STATUS_SUCCESS
     

The offload target successfully invalidated the state objects.

</li>
<li>
NDIS_STATUS_FAILURE
     

The invalidate operation did not succeed. In this case, the offload target has stopped responding (is
     hung).

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/nc-ndischimney-w_invalidate_offload_handler">MiniportInvalidateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
 

 

