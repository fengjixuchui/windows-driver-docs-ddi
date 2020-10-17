---
UID: NF:ks.KsFilterRegisterPowerCallbacks
title: KsFilterRegisterPowerCallbacks function (ks.h)
description: The KsFilterRegisterPowerCallbacks function registers power management callbacks for Filter.
old-location: stream\ksfilterregisterpowercallbacks.htm
tech.root: stream
ms.assetid: 9b4a7932-7371-48d2-95fb-1c3e3ca170be
ms.date: 04/23/2018
keywords: ["KsFilterRegisterPowerCallbacks function"]
ms.keywords: KsFilterRegisterPowerCallbacks, KsFilterRegisterPowerCallbacks function [Streaming Media Devices], avfunc_7c5322b7-f7e2-4641-b466-06f5d9ebfc34.xml, ks/KsFilterRegisterPowerCallbacks, stream.ksfilterregisterpowercallbacks
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterRegisterPowerCallbacks
 - ks/KsFilterRegisterPowerCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFilterRegisterPowerCallbacks
---

# KsFilterRegisterPowerCallbacks function


## -description

The **KsFilterRegisterPowerCallbacks** function registers power management callbacks for *Filter*.

## -parameters

### -param Filter 

[in]
A pointer to the [KSFILTER](./ns-ks-_ksfilter.md) structure for which to register power callbacks. In order to receive power notification messages, *Filter* must be filter-centric.

### -param Sleep 

[in, optional]
A pointer to a function that handles sleep requests for the device. If **NULL**, no sleep callback is registered. For more information, see the Remarks section below.

### -param Wake 

[in, optional]
A pointer to a function that handles wake requests for the device. If **NULL**, no wake callback is specified. For more information, see the Remarks section below.

## -remarks

> [!WARNING]
> Do not attempt to obtain the filter control mutex* from within either the Sleep or Wake callback, or deadlock may occur. For more information about mutexes, read [Mutexes in AVStream](/windows-hardware/drivers/stream/mutexes-in-avstream).

The two callbacks should be prototyped as follows:

```cpp
void Sleep/Wake (IN PKSFILTER Filter, IN DEVICE_POWER_STATE State);
```

The *Sleep* callback is made if *Filter* is a filter-centric filter and the device is going to sleep. The *Wake* callback is made if *Filter* is a filter-centric filter and the device is waking.

For information about device power states, see [Device Power States](/windows-hardware/drivers/kernel/device-power-states).

Also see [Initializing an AVStream Minidriver](/windows-hardware/drivers/stream/initializing-an-avstream-minidriver) and [Filter-Centric Processing](/windows-hardware/drivers/stream/filter-centric-processing).

## -see-also

[KsPinRegisterPowerCallbacks](./nf-ks-kspinregisterpowercallbacks.md)