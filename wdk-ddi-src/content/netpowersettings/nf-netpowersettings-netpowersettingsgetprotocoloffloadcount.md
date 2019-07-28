---
UID: NF:netpowersettings.NetPowerSettingsGetProtocolOffloadCount
title: NetPowerSettingsGetProtocolOffloadCount function (netpowersettings.h)
description: Retrieves the number of protocol offload structures associated with a NETPOWERSETTINGS object.
tech.root: netvista
ms.assetid: eb4ff3a2-296f-4011-8475-abc9e0006659
ms.date: 02/08/2018
ms.topic: function
f1_keywords:
 - "netpowersettings/NetPowerSettingsGetProtocolOffloadCount"
ms.keywords: NetPowerSettingsGetProtocolOffloadCount
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
- NetPowerSettingsGetProtocolOffloadCount
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetPowerSettingsGetProtocolOffloadCount function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Retrieves the number of protocol offload structures associated with a NETPOWERSETTINGS object.

## -parameters

### -param NetPowerSettings
A handle to the NETPOWERSETTINGS object associated with the net adapter. To retrieve the handle, call [NetAdapterGetPowerSettings](../netadapter/nf-netadapter-netadaptergetpowersettings.md).

## -returns
Returns the total number of enabled and disabled protocol offload structures associated with a NETPOWERSETTINGS object.

## -remarks
The client driver must only call **NetPowerSettingsGetProtocolOffloadCount** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_ADAPTER_PREVIEW_PROTOCOL_OFFLOAD](../netadapter/nc-netadapter-evt_net_adapter_preview_protocol_offload.md)* callback function. Otherwise, the call results in a system bugcheck.

To determine if a specific protocol offload is enabled, call [NetPowerSettingsIsProtocolOffloadEnabled](nf-netpowersettings-netpowersettingsisprotocoloffloadenabled.md).



## -see-also
