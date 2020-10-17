---
UID: NC:wlanihv.DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES
title: DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extqueryvirtualstationproperties.htm
tech.root: netvista
ms.assetid: 4ea71ef7-c897-413c-a542-e8068bcc66a6
ms.date: 02/16/2018
keywords: ["DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES callback"]
ms.keywords: DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES, Dot11ExtQueryVirtualStationProperties, Dot11ExtQueryVirtualStationProperties callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_c8da5f60-0502-4381-b9e4-f9b8e245e5e8.xml, netvista.dot11extqueryvirtualstationproperties, wlanihv/Dot11ExtQueryVirtualStationProperties
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
f1_keywords:
 - DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES
 - wlanihv/DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wlanihv.h
api_name:
 - Dot11ExtQueryVirtualStationProperties
---

# DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES callback


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtQueryVirtualStationProperties</b> function to query the properties of a
  virtual 802.11 station.

## -parameters

### -param hDot11SvcHandle 

[in, optional]
A handle used by the operating system to reference the primary physical wireless LAN (WLAN)
     adapter. This handle value was received as the
     <i>hDot11SvcHandle</i> parameter through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

### -param pbIsVirtualStation 

[out]
A pointer to a Boolean value that indicates whether the primary physical WLAN adapter pointed to
     by the
     <i>hDot11SvcHandle</i> parameter is a virtual station adapter or not. If the value is <b>TRUE</b>, the queried
     adapter is a virtual station, otherwise it is not a virtual station.

### -param pgPrimary 

[out]
A pointer to a GUID value that identifies the primary physical WLAN adapter that hosts a virtual
     station. This parameter is valid only if
     <i>pbIsVirtualStation</i> points to a value that is <b>TRUE</b>.

### -param pvReserved

This parameter is reserved for use by the operating system and should be <b>NULL</b>.

## -returns

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.

## -prototype

```cpp
DWORD WINAPI * Dot11ExtQueryVirtualStationProperties(
  _In_opt_   HANDLE hDot11SvcHandle,
  _Out_      BOOL   *pbIsVirtualStation,
  _Out_      GUID   *pgPrimary,
  _Reserved_ LPVOID pvReserved
);
```

## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>