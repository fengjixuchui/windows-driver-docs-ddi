---
UID: NS:netadapter._NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES
title: NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES (netadapter.h)
description: The NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a magic packet.
tech.root: netvista
ms.assetid: 275f7fe2-1bfc-4a88-b3c7-b78840b34930
ms.date: 10/25/2019
keywords: ["NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES structure"]
ms.keywords: NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES, NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES,
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
req.typenames: NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES
 - netadapter/_NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES
 - NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES
 - netadapter/NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES
product:
 - Windows
---

# NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES structure


## -description

The **NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES** structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a magic packet.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field MagicPacket

A boolean value that describes if the net adapter is capable of waking from a magic packet.

## -remarks

Call [**NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_magic_packet_capabilities_init.md) to initialize this structure, then call [**NetAdapterWakeSetMagicPacketCapabilities**](../netadapter/nf-netadapter-netadapterwakesetmagicpacketcapabilities.md) to set the net adapter's magic packet WoL capabilities. Client drivers typically call **NetAdapterWakeSetMagicPacketCapabilities** when starting a net adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_magic_packet_capabilities_init.md)

[**NetAdapterWakeSetMagicPacketCapabilities**](../netadapter/nf-netadapter-netadapterwakesetmagicpacketcapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)