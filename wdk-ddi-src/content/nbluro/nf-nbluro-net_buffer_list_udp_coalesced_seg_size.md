---
UID: NF:nbluro.NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE
tech.root: netvista
title: NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE
ms.date: 02/28/2024
targetos: Windows
description: NDIS drivers use NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE to get and set the size, in bytes, of the individual UDP datagram payloads that were coalesced into a single NET_BUFFER_LIST structure.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/nbluro.h
req.idl: 
req.include-header: ndis.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
returns-override: true
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nbluro.h
api_name:
 - NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE
f1_keywords:
 - NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE
 - nbluro/NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE
dev_langs:
 - c++
helpviewer_keywords:
 - NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE
---

## -description

NDIS drivers use the **NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE** macro to get and set the size, in bytes, of the individual UDP datagram payloads that were coalesced into a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure. The datagrams must have the same payload length in order to be eligible for coalescing, with the exception of the last datagram which may be less.

## -syntax

```cpp
#define NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE(_NBL) \
    (((NDIS_UDP_RSC_OFFLOAD_NET_BUFFER_LIST_INFO*) \
        &(_NBL)->NetBufferListInfo[UdpRecvSegCoalesceOffloadInfo])->Receive.SegSize)
```

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE** returns the **SegSize** member of the [**NDIS_UDP_RSC_OFFLOAD_NET_BUFFER_LIST_INFO**](../nbluro/ns-nbluro-ndis_udp_rsc_offload_net_buffer_list_info.md) structure that is associated with the **UdpRecvSegCoalesceOffloadInfo** identifier. The information is retrieved from the **NetBufferListInfo** member of the indicated **NET_BUFFER_LIST** structure.

## -remarks

The following example demonstrates getting a **SegSize** value:

```cpp
value = NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE(Nbl);
```

The following example demonstrates setting a **SegSize** value:

```cpp
NET_BUFFER_LIST_UDP_COALESCED_SEG_SIZE(Nbl) = 1200;
```

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

[UDP Receive Segment Coalescing Offload (URO)](/windows-hardware/drivers/network/udp-rsc-offload)