---
UID: NF:netadapteroffload.NetOffloadIsLsoIPv6Enabled
title: NetOffloadIsLsoIPv6Enabled function (netadapteroffload.h)
description: The NetOffloadIsLsoIPv6Enabled function determines whether a net adapter has LSO offload enabled for IPv6 packets.
tech.root: netvista
ms.assetid: 74d6ba64-7825-488f-818d-e54994d56930
ms.date: 01/17/2019
keywords: ["NetOffloadIsLsoIPv6Enabled function"]
ms.keywords: NetOffloadIsLsoIPv6Enabled
req.header: netadapteroffload.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
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
f1_keywords:
 - NetOffloadIsLsoIPv6Enabled
 - netadapteroffload/NetOffloadIsLsoIPv6Enabled
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetOffloadIsLsoIPv6Enabled
---

# NetOffloadIsLsoIPv6Enabled function


## -description

The **NetOffloadIsLsoIPv6Enabled** function determines whether a net adapter has LSO offload enabled for IPv6 packets.

## -parameters

### -param Offload

A NETOFFLOAD object that represents the net adapter's LSO capabilities.

## -returns

Returns **TRUE** if LSO offload is enabled for IPv6 packets, or **FALSE** if it is not.

## -remarks

Client drivers typically call this function during their [*EvtNetAdapterOffloadSetLso*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_lso.md) callback to test whether an updated set of active LSO capabilities includes LSO offload for IPv6 packets.

## -see-also

[NetAdapterCx hardware offloads](/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[*EVT_NET_ADAPTER_OFFLOAD_SET_LSO*](../netadapteroffload/nc-netadapteroffload-evt_net_adapter_offload_set_lso.md)