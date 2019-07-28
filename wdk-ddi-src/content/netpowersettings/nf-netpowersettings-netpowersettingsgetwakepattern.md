---
UID: NF:netpowersettings.NetPowerSettingsGetWakePattern
title: NetPowerSettingsGetWakePattern function (netpowersettings.h)
description: Retrieves the wake pattern structure at the specified index.
tech.root: netvista
ms.assetid: babd5f84-dcc0-4800-a73b-3dbf580700e0
ms.date: 02/08/2018
ms.topic: function
f1_keywords:
 - "netpowersettings/NetPowerSettingsGetWakePattern"
ms.keywords: NetPowerSettingsGetWakePattern
req.header: netpowersettings.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib: NetAdapterCxStub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netpowersettings.h
api_name: 
- NetPowerSettingsGetWakePattern
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetPowerSettingsGetWakePattern function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Retrieves the wake pattern structure at the specified index.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).


### -param Index
A zero-based value that is used as an index into the WoL patterns stored in the NETPOWERSETTINGS object. This value must be less than the value returned by [NetPowerSettingsGetWakePatternCount](nf-netpowersettings-netpowersettingsgetwakepatterncount.md).

## -returns
Returns a pointer to the [NDIS_PM_WOL_PATTERN](../ntddndis/ns-ntddndis-_ndis_pm_wol_pattern.md) structure at the specified index, or **NULL** if the index value is invalid.

## -remarks
The client driver must only call **NetPowerSettingsGetWakePattern** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_ADAPTER_PREVIEW_WAKE_PATTERN](../netadapter/nc-netadapter-evt_net_adapter_preview_wake_pattern.md)* callback function. Otherwise, the call results in a system bugcheck.

The client can check if this pattern is enabled by calling [NetPowerSettingsIsWakePatternEnabled](nf-netpowersettings-netpowersettingsiswakepatternenabled.md).

The client driver can use the pointer to examine the [NDIS_PM_WOL_PATTERN](../ntddndis/ns-ntddndis-_ndis_pm_wol_pattern.md) structure, but should not retain it. NetAdapterCx automatically releases the pattern structure during WoL pattern removal.



## -see-also

[NDIS_PM_WOL_PATTERN](../ntddndis/ns-ntddndis-_ndis_pm_wol_pattern.md)
