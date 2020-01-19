---
UID: NS:netadapter._NET_ADAPTER_TX_CAPABILITIES
title: _NET_ADAPTER_TX_CAPABILITIES (netadapter.h)
description: The NET_ADAPTER_TX_CAPABILITIES structure describes the transmit capabilities of a net adapter.
tech.root: netvista
ms.assetid: dd7810b6-12cc-46d3-9b74-2eabede35831
ms.date: 09/27/2019
ms.topic: struct
f1_keywords:
 - "netadapter/NET_ADAPTER_POWER_CAPABILITIES"
ms.keywords: _NET_ADAPTER_TX_CAPABILITIES, NET_ADAPTER_TX_CAPABILITIES, *PNET_ADAPTER_TX_CAPABILITIES, 
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_ADAPTER_TX_CAPABILITIES, *PNET_ADAPTER_TX_CAPABILITIES
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- netadapter.h
apiname: 
- _NET_ADAPTER_TX_CAPABILITIES
product:
- Windows
targetos: Windows
---

# _NET_ADAPTER_TX_CAPABILITIES structure

## -description

The **NET_ADAPTER_TX_CAPABILITIES** structure describes the transmit capabilities of a net adapter.

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field MappingRequirement

A [**NET_MEMORY_MAPPING_REQUIREMENT**](ne-netadapter-_net_memory_mapping_requirement.md) value that specifies how the operating system should map transmit data buffers.

### -field PayloadBackfill

The amount of space, in bytes, reserved for the client driver before the start of each [**NET_PACKET**](../packet/ns-packet-_net_packet.md)'s payload.

### -field MaximumNumberOfFragments

The maximum number of fragments per packet that the adapter can handle, or `((SIZE_T) - 1)` if there is no limit.
 
### -field FragmentBufferAlignment

The minimum alignment for packet fragments. This member must be a power of 2.
 
### -field FragmentRingNumberOfElementsHint

A hint indicating how many elements the adapter wants for each transmit queue's [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) ring buffer. This member must be a power of 2.
 
### -field MaximumNumberOfQueues

The maximum number of transmit queues that the adapter supports.
 
### -field DmaCapabilities

A pointer to a driver-allocated and initialized [**NET_DMA_CAPABILITIES**](ns-netadapter-_net_adapter_dma_capabilities.md) structure that describes the adapter's DMA capabilities on the transmit path. This member is ignored by NetAdapterCx if **MappingRequirement** is not set to **NetMemoryMappingRequirementDmaMapped**. 

## -remarks

Call one of the NET_ADAPTER_TX_CAPABILITIES_INIT_*XXX* methods to initialize this structure. For more info about each initialization method, see the links in the See Also section. 

An initialized **NET_ADAPTER_TX_CAPABILITIES** structure is passed as a parameter to [**NetAdapterSetDatapathCapabilities**](nf-netadapter-netadaptersetdatapathcapabilities.md).

## -see-also

[**NET_ADAPTER_TX_CAPABILITIES_INIT**](nf-netadapter-net_adapter_tx_capabilities_init.md)

[**NET_ADAPTER_TX_CAPABILITIES_INIT_FOR_DMA**](nf-netadapter-net_adapter_tx_capabilities_init_for_dma.md)
