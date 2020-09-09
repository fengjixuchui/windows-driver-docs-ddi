---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE
title: EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE (netreceivescaling.h)
description: The EvtNetAdapterReceiveScalingEnable callback function is implemented by the client driver to enable receive side scaling (RSS) for a network interface controller (NIC).
tech.root: netvista
ms.assetid: 3c249ff6-2a88-4b73-9f04-b3be1a2996d9
ms.date: 03/08/2018
keywords: ["EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE callback function"]
req.header: netreceivescaling.h
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
targetos: Windows
f1_keywords:
 - EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE
 - netreceivescaling/EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - netreceivescaling.h
api_name:
 - EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE callback function


## -description

The *EvtNetAdapterReceiveScalingDisable* callback function is implemented by the client driver to disable receive side scaling (RSS) for a network interface controller (NIC).

## -parameters

### -param Adapter 

The **NETADAPTER** object the client driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

## -prototype

```cpp
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE EvtNetAdapterReceiveScalingDisable; 

// Definition

VOID EvtNetAdapterReceiveScalingDisable 
(
	_In_ NETADAPTER Adapter
)
{...}

typedef EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE *PFN_NET_ADAPTER_RECEIVE_SCALING_DISABLE;
```

## -remarks

Register your implementation of this callback function by setting the appropriate member of the [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure and then calling [NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md).Client drivers typically call **NetAdapterSetReceiveScalingCapabilities** when starting a net adapter, before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).



### Example

In this callback, client drivers disable RSS on the NIC.

> [!IMPORTANT]
> Client drivers should **not** clear or reset their indirection table from their *EvtNetAdapterReceiveScalingDisable* callback. The framework will set the driver's initial indirection table state.

```C++
VOID
MyEvtNetAdapterReceiveScalingDisable(
	_In_ NETADAPTER Adapter
)
{
	if(!MyHardwareRssSetControl(MY_RSS_MULTI_CPU_DISABLE))
	{
		WdfDeviceSetFailed(Adapter->WdfDevice, WdfDeviceFailedAttemptRestart);
	}
}
```

## -see-also

*[EvtNetAdapterReceiveScalingEnable](nc-netreceivescaling-evt_net_adapter_receive_scaling_enable.md)*

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)

