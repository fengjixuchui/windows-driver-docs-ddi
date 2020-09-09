---
UID: NF:netwakesource.NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT
title: NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT function (netwakesource.h)
author: windows-driver-content
description: The NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT function initializes a NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS structure.
tech.root: netvista
ms.assetid: 096314c3-db04-4d4d-bab4-697ce4edd6fe
ms.author: windowsdriverdev
ms.date: 10/07/2019
keywords: ["NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT function"]
ms.keywords: NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT
req.header: netwakesource.h
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
 - NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT
 - netwakesource/NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netwakesource.h
api_name:
 - NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT
product:
 - Windows
---

# NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT function


## -description

The **NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT** function initializes a [**NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS**](../netwakesource/ns-netwakesource-_net_wake_source_media_change_parameters.md) structure.

## -parameters

### -param Parameters

A pointer to a driver-allocated [**NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS**](../netwakesource/ns-netwakesource-_net_wake_source_media_change_parameters.md) structure.

## -returns

This function does not return a value.

## -remarks

This function zeroes out the memory of the **NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS** structure, then fills in the **Size** member. Client drivers must then call [**NetWakeSourceGetMediaChangeParameters**](../netwakesource/nf-netwakesource-netwakesourcegetmediachangeparameters.md) to fill in the other members of the structure.

The client driver must only call **NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS**](../netwakesource/ns-netwakesource-_net_wake_source_media_change_parameters.md)

