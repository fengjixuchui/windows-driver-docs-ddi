---
UID: NF:netadapterpacket.NET_EXTENSION_QUERY_INIT
title: NET_EXTENSION_QUERY_INIT function (netadapterpacket.h)
description: The NET_EXTENSION_QUERY_INIT function initializes a NET_EXTENSION_QUERY structure.
tech.root: netvista
ms.assetid: 3af300cf-1518-49bc-8192-9fa3e6c64981
ms.date: 11/07/2019
keywords: ["NET_EXTENSION_QUERY_INIT function"]
ms.keywords: NET_EXTENSION_QUERY_INIT
req.header: netadapterpacket.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NET_EXTENSION_QUERY_INIT
 - netadapterpacket/NET_EXTENSION_QUERY_INIT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapterpacket.h
api_name:
 - NET_EXTENSION_QUERY_INIT
product:
 - Windows
---

# NET_EXTENSION_QUERY_INIT function


## -description

The **NET_EXTENSION_QUERY_INIT** function initializes a [**NET_EXTENSION_QUERY**](../netadapterpacket/ns-netadapterpacket-_net_extension_query.md) structure.

## -parameters

### -param Extension

A pointer to a driver-allocated [**NET_EXTENSION_QUERY**](../netadapterpacket/ns-netadapterpacket-_net_extension_query.md) structure.

### -param Name

The name of the extension to be queried.

### -param Version

The version of the extension to be queried.

### -param Type

A [**NET_EXTENSION_TYPE**](../extension/ne-extension-_net_extension_type.md) value that specifies the type of extension being queried.

## -returns

This function does not return a value.

## -remarks

After calling this function, pass the initialized **NET_EXTENSION_QUERY** structure to **NetTx(Rx)QueueGetExtension** to get the offset to that extension in the packet or fragment descriptor.

To prevent re-querying extension offsets too often, call this function and **NetTx(Rx)QueueGetExtension** from the *EvtNetAdapterCreateTx(Rx)Queue* callback function after calling **NetTx(Rx)QueueCreate**, then store the offset in a queue context space.

For more info about extensions, see [Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions). 

For a code example of querying extension offsets, see [Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues).

## -see-also

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[**NET_EXTENSION_QUERY**](../netadapterpacket/ns-netadapterpacket-_net_extension_query.md)

[**NET_EXTENSION_TYPE**](../extension/ne-extension-_net_extension_type.md)