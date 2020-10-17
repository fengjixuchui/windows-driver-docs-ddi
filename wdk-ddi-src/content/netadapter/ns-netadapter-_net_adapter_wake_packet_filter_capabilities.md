---
UID: NS:netadapter._NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES
title: NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES (netadapter.h)
description: The NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a packet filter match.
tech.root: netvista
ms.assetid: 4c04cbbb-a926-4371-a717-bfe6bf0742c4
ms.date: 11/07/2019
keywords: ["NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES structure"]
ms.keywords: NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES, NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES,
req.header: netadapter.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES
 - netadapter/_NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES
 - NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES
 - netadapter/NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES
product:
 - Windows
---

# NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES structure


## -description

The **NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES** structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a packet filter match.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field PacketFilterMatch

A boolean value that describes if the net adapter is capable of waking from a packet filter match.

## -remarks

Call [**NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_packet_filter_capabilities_init.md) to initialize this structure, then call [**NetAdapterWakeSetPacketFilterCapabilities**](../netadapter/nf-netadapter-netadapterwakesetpacketfiltercapabilities.md) to set the net adapter's packet filter WoL capabilities. Client drivers typically call **NetAdapterWakeSetPacketFilterCapabilities** when starting a net adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_packet_filter_capabilities_init.md)

[**NetAdapterWakeSetPacketFilterCapabilities**](../netadapter/nf-netadapter-netadapterwakesetpacketfiltercapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)