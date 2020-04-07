---
UID: NF:netwakesource.NetWakeSourceGetBitmapParameters
title: NetWakeSourceGetBitmapParameters function (netwakesource.h)
author: windows-driver-content
description: The NetWakeSourceGetBitmapParameters method gets parameters for a bitmap pattern wake-on-LAN (WoL) source.
tech.root: netvista
ms.assetid: 766add6b-02a7-40b2-abfa-d30d3a24b067
ms.author: windowsdriverdev
ms.date: 10/07/2019
keywords: ["NetWakeSourceGetBitmapParameters function"]
f1_keywords:
 - "netwakesource/NetWakeSourceGetBitmapParameters"
ms.keywords: NetWakeSourceGetBitmapParameters
req.header: netwakesource.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
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
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetWakeSourceGetBitmapParameters
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetWakeSourceGetBitmapParameters function


## -description

The **NetWakeSourceGetBitmapParameters** method gets parameters for a bitmap pattern wake-on-LAN (WoL) source.

## -parameters

### -param WakeSource

A NETWAKESOURCE object that represents this bitmap pattern wake source.

### -param Parameters

A pointer to a driver-allocated and initialized [**NET_WAKE_SOURCE_BITMAP_PARAMETERS**](../netwakesource/ns-netwakesource-_net_wake_source_bitmap_parameters.md) structure that receives the bitmap pattern parameters.

## -returns

This method does not return a value.

## -remarks

Call [**NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT**](../netwakesource/nf-netwakesource-net_wake_source_bitmap_parameters_init.md) to initialize the [**NET_WAKE_SOURCE_BITMAP_PARAMETERS**](../netwakesource/ns-netwakesource-_net_wake_source_bitmap_parameters.md) structure before calling this method.

The client driver must only call **NetWakeSourceGetBitmapParameters** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_BITMAP_PARAMETERS**](../netwakesource/ns-netwakesource-_net_wake_source_bitmap_parameters.md)

[**NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT**](../netwakesource/nf-netwakesource-net_wake_source_bitmap_parameters_init.md)
