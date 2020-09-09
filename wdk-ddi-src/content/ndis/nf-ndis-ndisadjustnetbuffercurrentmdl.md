---
UID: NF:ndis.NdisAdjustNetBufferCurrentMdl
title: NdisAdjustNetBufferCurrentMdl function (ndis.h)
description: The NdisAdjustNetBufferCurrentMdl function updates a NET_BUFFER structure based on the current data offset.
old-location: netvista\ndisadjustnetbuffercurrentmdl.htm
tech.root: netvista
ms.assetid: 5d05793b-cb35-435d-aa59-6ac380668d91
ms.date: 05/02/2018
keywords: ["NdisAdjustNetBufferCurrentMdl function"]
ms.keywords: NdisAdjustNetBufferCurrentMdl, NdisAdjustNetBufferCurrentMdl function [Network Drivers Starting with Windows Vista], ndis/NdisAdjustNetBufferCurrentMdl, ndis_netbuf_functions_ref_a555c8dc-ed71-46b9-8922-32bfad03f2a1.xml, netvista.ndisadjustnetbuffercurrentmdl
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisAdjustNetBufferCurrentMdl
 - ndis/NdisAdjustNetBufferCurrentMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisAdjustNetBufferCurrentMdl
---

# NdisAdjustNetBufferCurrentMdl function


## -description

The 
  <b>NdisAdjustNetBufferCurrentMdl</b> function updates a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure based on the current data
  offset.

## -parameters

### -param NetBuffer 

[in]
A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -remarks

The 
    <b>NdisAdjustNetBufferCurrentMdl</b> function recalculates and sets the 
    <b>CurrentMdl</b> and 
    <b>CurrentMdlOffset</b> members of a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure based on the 
    <b>DataOffset</b> member of the NET_BUFFER structure.

Callers of 
    <b>NdisAdjustNetBufferCurrentMdl</b> can run at any IRQL, but typically run at IRQL <=
    DISPATCH_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>

