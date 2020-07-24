---
UID: NF:ndis.NET_BUFFER_LIST_NBL_FLAGS
title: NET_BUFFER_LIST_NBL_FLAGS macro (ndis.h)
description: The NET_BUFFER_LIST_NBL_FLAGS macro retrieves the NblFlags member of a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: dee43a1e-5815-4324-8d8e-f928fdffdae6
ms.date: 04/13/2018
keywords: ["NET_BUFFER_LIST_NBL_FLAGS macro"]
f1_keywords:
 - "ndis/NET_BUFFER_LIST_NBL_FLAGS"
 - "NET_BUFFER_LIST_NBL_FLAGS"
ms.keywords: NET_BUFFER_LIST_NBL_FLAGS
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndis.h
api_name: 
- NET_BUFFER_LIST_NBL_FLAGS
targetos: Windows

---

# NET_BUFFER_LIST_NBL_FLAGS macro


## -description

The **NET_BUFFER_LIST_NBL_FLAGS** macro retrieves the **NblFlags** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -remarks

NDIS network drivers should use the **NET_BUFFER_LIST_NBL_FLAGS** macro to get the **NblFlags** member of a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -see-also

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
