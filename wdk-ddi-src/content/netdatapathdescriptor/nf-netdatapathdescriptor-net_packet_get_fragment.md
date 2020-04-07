---
UID: NF:netdatapathdescriptor.NET_PACKET_GET_FRAGMENT
title: NET_PACKET_GET_FRAGMENT macro (netdatapathdescriptor.h)
description: The NET_PACKET_GET_FRAGMENT macro retrieves a single fragment from a net packet.
tech.root: netvista
ms.assetid: ee42c2b6-078c-493e-8b47-67aecffc7be7
ms.date: 02/27/2018
keywords: ["NET_PACKET_GET_FRAGMENT macro"]
f1_keywords:
 - "netdatapathdescriptor/NET_PACKET_GET_FRAGMENT"
ms.keywords: NET_PACKET_GET_FRAGMENT
req.header: netdatapathdescriptor.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib: netdatapathdescriptor.h
req.dll:
req.irql: PASSIVE_LEVEL
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
- netdatapathdescriptor.h
api_name: 
- NET_PACKET_GET_FRAGMENT
product:
- Windows
targetos: Windows

---

# NET_PACKET_GET_FRAGMENT macro


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_PACKET_GET_FRAGMENT** macro retrieves a single fragment from a net packet.

## -parameters

### -param packet
A pointer to the [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md) to which the fragment belongs.

### -param desc
A pointer to the datapath queue's [NET_DATAPATH_DESCRIPTOR](ns-netdatapathdescriptor-_net_datapath_descriptor.md) structure.

### -param index
The index of the fragment in the datapath queue's fragment ring buffer, relative to the parent packet.

## -remarks
[NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md)s are organized in a ring buffer just like [NET_PACKET](../netpacket/ns-netpacket-_net_packet.md)s. Each packet in the packet ring buffer references the start of its fragments in the fragment ring buffer. Because fragments are contained within a packet, this means that the *index* parameter of this macro is the index of the fragment *within* the packet and not in the overall fragment ring buffer. 

For example, consider a NIC driver that wants to check information about an Ethernet frame on its transmit queue. First, the driver can use the 0th index of the packet and call **NET_PACKET_GET_FRAGMENT** to check the first fragment and make sure the Ethernet header is there. Then, it can loop over the fragments in the packet calling **NET_PACKET_GET_FRAGMENT** on each one to find out the total data length.

```C++
...

// Verify the first fragment has the Ethernet header
NET_PACKET_FRAGMENT* fragment = NET_PACKET_GET_FRAGMENT(packet, descriptor, 0);
if(fragment->ValidLength < sizeof(ETHERNET_HEADER))
{
    return;
}

// Obtain the total length of the fragments in this packet
ULONG dataLength = 0;
for(UINT32 i = 0; i < packet->FragmentCount; i++)
{
    fragment = NET_PACKET_GET_FRAGMENT(packet, descriptor, i);
    dataLength += (ULONG)fragment->ValidLength;
}

...

```



## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)
