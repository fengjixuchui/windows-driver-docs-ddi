---
UID: NF:ringcollection.NetRingCollectionGetFragmentRing
title: NetRingCollectionGetFragmentRing function (ringcollection.h)
description: The NetRingCollectionGetFragmentRing gets the fragment ring for a packet queue.
tech.root: netvista
ms.assetid: 4A88C04C-0E0C-4B93-80CB-4C510802F7CC
ms.date: 02/06/2019
ms.topic: function
f1_keywords:
 - "ringcollection/RILWRITEPHONEBOOKENTRYPARAMS"
ms.keywords: NetRingCollectionGetFragmentRing
req.header: ringcollection.h
req.include-header: netadaptercx.h
req.target-type: Universal
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
req.alt-api:
req.alt-loc:
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	ringcollection.h
apiname: 
-	NetRingCollectionGetFragmentRing
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetRingCollectionGetFragmentRing function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NetRingCollectionGetFragmentRing** gets the fragment ring for a packet queue.

## -parameters

### -param Rings

A pointer to a [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure that describes this packet queue's net rings.

## -returns

Returns a pointer to the fragment [**NET_RING**](../ring/ns-ring-_net_ring.md) for the packet queue.

## -remarks

Client drivers typically call this method when they need to work with a fragment ring directly, such as when the driver is posting information to hardware. For example, during transmit a driver might use the fragment ring's **ElementIndexMask** to retrieve the correct fragment that is being posted to hardware in order to populate the hardware descriptor. 

For examples of using this method, see the [Realtek sample driver](https://github.com/Microsoft/NetAdapter-Cx-Driver-Samples/tree/release_1809/RtEthSample).

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)
