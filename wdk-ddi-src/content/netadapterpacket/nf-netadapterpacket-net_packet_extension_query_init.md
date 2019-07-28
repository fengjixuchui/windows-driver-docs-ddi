---
UID: NF:netadapterpacket.NET_PACKET_EXTENSION_QUERY_INIT
title: NET_PACKET_EXTENSION_QUERY_INIT function (netadapterpacket.h)
description: The NET_PACKET_EXTENSION_QUERY_INIT method initializes a NET_PACKET_EXTENSION_QUERY structure.
tech.root: netvista
ms.assetid: 79787ad3-8183-46be-9d37-75223947bbc2
ms.date: 03/01/2018
ms.topic: function
f1_keywords:
 - "netadapterpacket/NET_PACKET_EXTENSION_INIT"
ms.keywords: NET_PACKET_EXTENSION_QUERY_INIT
req.header: netadapterpacket.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NET_PACKET_EXTENSION_QUERY_INIT
product:
- Windows
targetos: Windows

---

# NET_PACKET_EXTENSION_QUERY_INIT function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NET_PACKET_EXTENSION_QUERY_INIT** method initializes a [NET_PACKET_EXTENSION_QUERY](ns-netadapterpacket-_net_packet_extension_query.md) structure.

## -parameters

### -param Extension
A pointer to the driver-allocated [NET_PACKET_EXTENSION_QUERY](ns-netadapterpacket-_net_packet_extension_query.md) structure.

### -param Name
The name of the extension to be queried.

### -param Version
The version of the extension to be queried.

## -returns
This method does not return a value.

## -remarks
After calling this method, pass the initialized [NET_PACKET_EXTENSION_QUERY](ns-netadapterpacket-_net_packet_extension_query.md) structure to **NetTx(Rx)QueueGetPacketExtensionOffset** to get the offset to that packet extension in the packet descriptor.

To prevent re-querying extension offsets too often, call this method and **NetTx(Rx)QueueGetPacketExtensionOffset** from the *EvtNetAdapterCreateTx(Rx)Queue* callback function after calling **NetTx(Rx)QueueCreate**, then store the offset in a queue context space.

For more information about packet extensions and available packet extension constants, see [Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions). For a code sample, see *[EvtNetAdapterCreateTxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_txqueue.md)* or *[EvtNetAdapterCreateRxQueue](../netadapter/nc-netadapter-evt_net_adapter_create_rxqueue.md)*.



## -see-also

[NetTxQueueGetExtension](../nettxqueue/nf-nettxqueue-nettxqueuegetextension.md)

[NetRxQueueGetExtension](../netrxqueue/nf-netrxqueue-netrxqueuegetextension.md)
