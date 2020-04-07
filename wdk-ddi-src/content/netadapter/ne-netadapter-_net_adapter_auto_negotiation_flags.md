---
UID: NE:netadapter._NET_ADAPTER_AUTO_NEGOTIATION_FLAGS
title: _NET_ADAPTER_AUTO_NEGOTIATION_FLAGS (netadapter.h)
description: Specifies the auto-negotiation settings for the NIC driver.
tech.root: netvista
ms.assetid: b7ae57e6-d3ce-409f-a737-ca303d1a58b1
ms.date: 09/27/2019
keywords: ["_NET_ADAPTER_AUTO_NEGOTIATION_FLAGS enumeration"]
f1_keywords:
 - "netadapter/NET_ADAPTER_AUTO_NEGOTIATION_FLAGS"
ms.keywords: _NET_ADAPTER_AUTO_NEGOTIATION_FLAGS, NET_ADAPTER_AUTO_NEGOTIATION_FLAGS, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_AUTO_NEGOTIATION_FLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NET_ADAPTER_AUTO_NEGOTIATION_FLAGS
targetos: Windows
product:
- Windows
---

# _NET_ADAPTER_AUTO_NEGOTIATION_FLAGS enumeration

## -description



Specifies the auto-negotiation settings for the NIC driver.

## -enum-fields

### -field NetAdapterAutoNegotiationFlagNone : 

No flags are set.

### -field NetAdapterAutoNegotiationFlagXmitLinkSpeedAutoNegotiated : 

The adapter has auto-negotiated the transmit link speed with the link partner.

### -field NetAdapterAutoNegotiationFlagRcvLinkSpeedautoNegotiated : 

The adapter has auto-negotiated the receive link speed with the link partner.

### -field NetAdapterAutoNegotiationFlagDuplexAutoNegotiated : 

The adapter has auto-negotiated the duplex state with the link partner.

### -field NetAdapterAutoNegotiationFlagPauseFunctionsAutoNegotiated : 

The adapter has auto-negotiated the pause functions with the link partner.

## -remarks

The **NET_ADAPTER_AUTO_NEGOTIATION_FLAGS** enumeration is used to specify auto-negotiation settings in the [**NET_ADAPTER_LINK_STATE**](ns-netadapter-_net_adapter_link_state.md) structure.

An initialized [**NET_ADAPTER_LINK_STATE**](ns-netadapter-_net_adapter_link_state.md) structure is an input to [**NetAdapterSetLinkState**](nf-netadapter-netadaptersetlinkstate.md).

## -see-also
