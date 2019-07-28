---
UID: NS:checksumtypes._NET_PACKET_CHECKSUM
title: _NET_PACKET_CHECKSUM (checksumtypes.h)
description: A NET_PACKET_CHECKSUM structure describes checksum information for a NET_PACKET.
tech.root: netvista
ms.assetid: 75363870-C58D-4677-A523-9728CB4A1BAC
ms.date: 01/30/2019
ms.topic: struct
f1_keywords:
 - "checksumtypes/BATTERY_INFORMATION"
ms.keywords: _NET_PACKET_CHECKSUM, NET_PACKET_CHECKSUM, *PNET_PACKET_CHECKSUM
req.header: checksumtypes.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_PACKET_CHECKSUM
topictype:
-	APIRef
apitype: 
-	HeaderDef
apilocation: 
-	checksumtypes.h
apiname: 
-	NET_PACKET_CHECKSUM
product:
- Windows
targetos: Windows
product:
- Windows
---

# _NET_PACKET_CHECKSUM structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

A **NET_PACKET_CHECKSUM** structure describes checksum information for a [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -struct-fields

### -field Layer2

A bit field that specifies a flag from either **NET_PACKET_TX_CHECKSUM_ACTION** or **NET_PACKET_RX_CHECKSUM_EVALUATION**. Targets the checksum field in the packet's layer 2 header.

### -field Layer3

A bit field that specifies a flag from either **NET_PACKET_TX_CHECKSUM_ACTION** or **NET_PACKET_RX_CHECKSUM_EVALUATION**. Targets the checksum field in the packet's layer 3 header.

### -field Layer4

A bit field that specifies a flag from either **NET_PACKET_TX_CHECKSUM_ACTION** or **NET_PACKET_RX_CHECKSUM_EVALUATION**. Targets the checksum field in the packet's layer 4 header.

### -field Reserved

Reserved for system use.

## -remarks

Client drivers can obtain this structure for a packet by calling [**NetExtensionGetPacketChecksum**](../checksum/nf-checksum-netextensiongetpacketchecksum.md).

For a transmit queue, the client specifies flag values from the **NET_PACKET_TX_CHECKSUM_ACTION** enumeration:

```c++
typedef enum _NET_PACKET_TX_CHECKSUM_ACTION
{
    NET_PACKET_TX_CHECKSUM_PASSTHROUGH                  = 0,
    NET_PACKET_TX_CHECKSUM_REQUIRED                     = 2,
} NET_PACKET_TX_CHECKSUM_ACTION;
```

For a receive queue, the client specifies flag values from the **NET_PACKET_RX_CHECKSUM_EVALUATION** enumeration:

```c++
typedef enum _NET_PACKET_RX_CHECKSUM_EVALUATION
{
    NET_PACKET_RX_CHECKSUM_NOT_CHECKED                  = 0,
    NET_PACKET_RX_CHECKSUM_VALID                        = 1,
    NET_PACKET_RX_CHECKSUM_INVALID                      = 2,
} NET_PACKET_RX_CHECKSUM_EVALUATION;
```

In a transmit queue, the client cross-references the **Checksum** information for a packet with the [**Layout**](../packet/ns-packet-_net_packet_layout.md) member of a [**NET_PACKET**](../packet/ns-packet-_net_packet.md) in order to determine which hardware transmit checksum offloads need to be enabled. A **NET_PACKET_TX_CHECKSUM_ACTION** value of **NET_PACKET_TX_CHECKSUM_REQUIRED** means that the client should perform the checksum calculation for this layer.

In a receive queue, the client converts its hardware packet descriptors' receive checksum offload fields into **NET_PACKET_RX_CHECKSUM_EVALUATION** values for each layer. **NET_PACKET_RX_CHECKSUM_VALID** indicates that the hardware determined that the checksum value is correct, while **NET_PACKET_RX_CHECKSUM_INVALID** means that it is incorrect. The default value is **NET_PACKET_RX_CHECKSUM_NOT_CHECKED**, which means that the checksum will be validated in software further up in the networking stack. The client should also fill out the [**Layout**](../packet/ns-packet-_net_packet_layout.md) member of the [**NET_PACKET**](../packet/ns-packet-_net_packet.md) structure.

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
