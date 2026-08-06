---
UID: NF:nbluro.NET_BUFFER_LIST_UDP_COALESCED_SEG_COUNT
tech.root: netvista
title: NET_BUFFER_LIST_UDP_COALESCED_SEG_COUNT
ms.date: 01/18/2024
targetos: Windows
description: The **NET_BUFFER_LIST_UDP_COALESCED_SEG_COUNT** macro returns the number of segments that were coalesced into a NET_BUFFER_LIST structure.
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
 - NET_BUFFER_LIST_UDP_COALESCED_SEG_COUNT
f1_keywords:
 - NET_BUFFER_LIST_UDP_COALESCED_SEG_COUNT
 - nbluro/NET_BUFFER_LIST_UDP_COALESCED_SEG_COUNT
dev_langs:
 - c++
helpviewer_keywords:
 - NET_BUFFER_LIST_UDP_COALESCED_SEG_COUNT
---

## -description

The **NET_BUFFER_LIST_UDP_COALESCED_SEG_COUNT** macro returns the number of segments that were coalesced into a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

## -returns

**NET_BUFFER_LIST_UDP_COALESCED_SEG_COUNT** returns the **SegCount** member of the [**NDIS_UDP_RSC_OFFLOAD_NET_BUFFER_LIST_INFO**](../nbluro/ns-nbluro-ndis_udp_rsc_offload_net_buffer_list_info.md) structure that is associated with the **UdpRecvSegCoalesceOffloadInfo** identifier. The information is retrieved from the **NetBufferListInfo** member of the indicated NET_BUFFER_LIST structure.

## -remarks

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

[**NDIS_UDP_RSC_OFFLOAD_NET_BUFFER_LIST_INFO**](../nbluro/ns-nbluro-ndis_udp_rsc_offload_net_buffer_list_info.md)

[UDP Receive Segment Coalescing Offload (URO)](/windows-hardware/drivers/network/udp-rsc-offload)