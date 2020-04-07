---
UID: NF:ring.NetRingAdvanceIndex
title: NetRingAdvanceIndex function (ring.h)
author: windows-driver-content
description: The NetRingAdvanceIndex method advances the index in a net ring forward, wrapping around if necessary.
tech.root: netvista
ms.assetid: 74b63740-6bf7-44e4-97bc-60392bc73d7c
ms.author: windowsdriverdev
ms.date: 09/25/2019
keywords: ["NetRingAdvanceIndex function"]
f1_keywords:
 - "ring/NetRingAdvanceIndex"
ms.keywords: NetRingAdvanceIndex
req.header: ring.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level as long as target memory is resident
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
- ring.h
api_name: 
- NetRingAdvanceIndex
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetRingAdvanceIndex function


## -description

The **NetRingAdvanceIndex** method advances the index in a net ring forward, wrapping around if necessary.

## -parameters

### -param Ring

A pointer to a [**NET_RING**](../ring/ns-ring-_net_ring.md) to access.

### -param Index

The index value to advance.

### -param Distance

The distance to advance the index.

## -returns

Returns the new index after advancing **Distance** forward in the net ring.

## -remarks

**NetRingAdvanceIndex** enables client drivers to move forward multiple indices in the net ring. Client drivers can also call the wrapper function [**NetRingIncrementIndex**](../ring/nf-ring-netringincrementindex.md) to increment the index by **1**.

## -see-also

[**NET_RING**](../ring/ns-ring-_net_ring.md)

[**NetRingIncrementIndex**](../ring/nf-ring-netringincrementindex.md)
