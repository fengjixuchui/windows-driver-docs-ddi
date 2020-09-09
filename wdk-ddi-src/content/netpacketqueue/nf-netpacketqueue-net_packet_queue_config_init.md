---
UID: NF:netpacketqueue.NET_PACKET_QUEUE_CONFIG_INIT
title: NET_PACKET_QUEUE_CONFIG_INIT function (netpacketqueue.h)
description: The NET_PACKET_QUEUE_CONFIG_INIT function initializes a NET_PACKET_QUEUE_CONFIG structure.
tech.root: netvista
ms.assetid: 5dd456ed-b2ec-4a60-8a43-0803a87eac84
ms.date: 07/16/2018
keywords: ["NET_PACKET_QUEUE_CONFIG_INIT function"]
ms.keywords: NET_PACKET_QUEUE_CONFIG_INIT
req.header: netpacketqueue.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.lib: netadaptercxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - NET_PACKET_QUEUE_CONFIG_INIT
 - netpacketqueue/NET_PACKET_QUEUE_CONFIG_INIT
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NET_PACKET_QUEUE_CONFIG_INIT
---

# NET_PACKET_QUEUE_CONFIG_INIT function


## -description

The **NET_PACKET_QUEUE_CONFIG_INIT** function initializes a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure.

## -parameters

### -param Config

A pointer to the driver-allocated [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure to initialize.

### -param EvtAdvance

A pointer to the client driver's implementation of the [*EVT_PACKET_QUEUE_ADVANCE*](nc-netpacketqueue-evt_packet_queue_advance.md) callback function for this packet queue.

### -param EvtSetNotificationEnabled

A pointer to the client driver's implementation of the [*EVT_PACKET_QUEUE_SET_NOTIFICATION_ENABLED*](nc-netpacketqueue-evt_packet_queue_advance.md) callback function for this packet queue.

### -param EvtCancel

A pointer to the client driver's implementation of the [*EVT_PACKET_QUEUE_CANCEL*](nc-netpacketqueue-evt_packet_queue_advance.md) callback function for this packet queue.

## -remarks

Client drivers must call this function to initialize a [**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md) structure before calling [**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md) or [**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md) to create a packet queue.

## -see-also

[**NET_PACKET_QUEUE_CONFIG**](ns-netpacketqueue-_net_packet_queue_config.md)

[**NetTxQueueCreate**](../nettxqueue/nf-nettxqueue-nettxqueuecreate.md)

[**NetRxQueueCreate**](../netrxqueue/nf-netrxqueue-netrxqueuecreate.md)

