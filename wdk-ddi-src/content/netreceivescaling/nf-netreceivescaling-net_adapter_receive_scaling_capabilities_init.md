---
UID: NF:netreceivescaling.NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT
title: NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT function (netreceivescaling.h)
description: The NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT function initializes a NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES structure.
tech.root: netvista
ms.assetid: 6ca814a1-599b-498c-af32-a21fe3359cd0
ms.date: 10/19/2018
keywords: ["NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT function"]
ms.keywords: NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT
req.header: netreceivescaling.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT
 - netreceivescaling/NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT
---

# NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT function


## -description

The **NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT** function initializes a [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure.

## -parameters

### -param Capabilities

A pointer to the driver-allocated [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure.

### -param NumberOfQueues

The number of hardware receive queues. This member must be a power of 2.

### -param UnhashedTargetType

A [NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_unhashed_target_type.md) value that indicates the type of handling for unhashed frames. If this member is set to **NetAdapterReceiveScalingUnhashedTargetTypeUnspecified**, then **UnhashedTarget** is ignored.

### -param HashTypes

A [NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_hash_type.md) value that indicates supported hash function types for calculating hash values.

### -param ProtocolTypes

A [NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_protocol_type.md) value that indicates the supported protocol types for calculating hash values.

### -param Enable

A pointer to the client driver's *[EvtNetAdapterReceiveScalingEnable](nc-netreceivescaling-evt_net_adapter_receive_scaling_enable.md)* event callback function.

### -param Disable

A pointer to the client driver's *[EvtNetAdapterReceiveScalingDisable](nc-netreceivescaling-evt_net_adapter_receive_scaling_disable.md)* event callback function.

### -param SetHashSecretKey

A pointer to the client driver's *[EvtNetAdapterReceiveScalingSetHashSecretKey](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_hash_secret_key.md)* event callback function.

### -param SetIndirectionEntries

A pointer to the client driver's *[EvtNetAdapterReceiveScalingSetIndirectionEntries](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_indirection_entries.md)* event callback function.

## -remarks

The [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure is an input parameter to [NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md). The client must use **NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT** to initialize this structure before calling **NetAdapterSetReceiveScalingCapabilities**.

## -see-also

[NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md)

[NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md)

[NetAdapterCx Receive Side Scaling](/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)