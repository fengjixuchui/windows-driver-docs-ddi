---
UID: NF:netringiterator.NetFragmentIteratorAdvance
title: NetFragmentIteratorAdvance function
author: windows-driver-content
description: The NetFragmentIteratorAdvance method advances the Index of a fragment iterator by one.
tech.root: netvista
ms.assetid: 45d1a44c-eab1-4f1a-9d17-3a0428151399
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetFragmentIteratorAdvance"
ms.keywords: NetFragmentIteratorAdvance
req.header: netringiterator.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
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
- netringiterator.h
api_name: 
- NetFragmentIteratorAdvance
product: Windows
targetos: Windows

---

# NetFragmentIteratorAdvance function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetFragmentIteratorAdvance** method advances the Index of a fragment iterator by one.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md) structure.

## -returns

None.

## -remarks

If the fragment iterator's current **Index** is at the end of the fragment ring, this method automatically handles wrapping around to the beginning of the ring.

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_FRAGMENT_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_fragment_iterator.md)
