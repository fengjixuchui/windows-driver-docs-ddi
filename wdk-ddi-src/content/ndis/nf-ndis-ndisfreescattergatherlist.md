---
UID: NF:ndis.NdisFreeScatterGatherList
title: NdisFreeScatterGatherList function (ndis.h)
description: The NdisFreeScatterGatherList function frees a scatter/gather list.
old-location: netvista\ndisfreescattergatherlist.htm
tech.root: netvista
ms.assetid: 140be989-e578-4bfe-8b9e-56abb274933a
ms.date: 05/02/2018
keywords: ["NdisFreeScatterGatherList function"]
ms.keywords: NdisFreeScatterGatherList, NdisFreeScatterGatherList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeScatterGatherList, ndis_shared_memory_ref_2376e740-d44c-4572-8731-7518d4765208.xml, netvista.ndisfreescattergatherlist
f1_keywords:
 - "ndis/NdisFreeScatterGatherList"
 - "NdisFreeScatterGatherList"
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
req.irql: = DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFreeScatterGatherList
targetos: Windows
req.typenames: 
---

# NdisFreeScatterGatherList function


## -description


The 
  <b>NdisFreeScatterGatherList</b> function frees a scatter/gather list.


## -parameters




### -param NdisHandle [in]

An NDIS driver or instance handle that was obtained during caller initialization. This should be
     the same handle that was passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisbuildscattergatherlist">
     NdisBuildScatterGatherList</a> function when the scatter/gather list was created.


### -param ScatterGatherListBuffer [in]

A pointer to a caller-provided 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a> structure to free.
     This must be the same buffer that was passed to the 
     <b>NdisBuildScatterGatherList</b> function when the scatter/gather list was allocated.


### -param WriteToDevice [in]

A BOOLEAN value that is set to <b>TRUE</b> if the scatter/gather list was used for writing to the device.
     Otherwise, it is <b>FALSE</b>.


## -remarks



NDIS drivers call the 
    <b>NdisFreeScatterGatherList</b> function to free a scatter/gather list that was created with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisbuildscattergatherlist">
    NdisBuildScatterGatherList</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisbuildscattergatherlist">NdisBuildScatterGatherList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a>
 

 

