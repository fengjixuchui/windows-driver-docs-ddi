---
UID: NE:windot11._DOT11_WPS_CONFIG_METHOD
title: _DOT11_WPS_CONFIG_METHOD (windot11.h)
description: The DOT11_WPS_CONFIG_METHOD enumeration specifies the Wi-Fi Protected Setup methods.
old-location: netvista\dot11_wps_config_method.htm
tech.root: netvista
ms.assetid: FFA5B3FF-57AF-4701-97FB-E1182CDE8F7A
ms.date: 02/16/2018
ms.keywords: "*PDOT11_WPS_CONFIG_METHOD, DOT11_WPS_CONFIG_METHOD, DOT11_WPS_CONFIG_METHOD enumeration [Network Drivers Starting with Windows Vista], DOT11_WPS_CONFIG_METHOD_DISPLAY, DOT11_WPS_CONFIG_METHOD_KEYPAD, DOT11_WPS_CONFIG_METHOD_NULL, DOT11_WPS_CONFIG_METHOD_PUSHBUTTON, _DOT11_WPS_CONFIG_METHOD, netvista.dot11_wps_config_method, windot11/DOT11_WPS_CONFIG_METHOD, windot11/DOT11_WPS_CONFIG_METHOD_DISPLAY, windot11/DOT11_WPS_CONFIG_METHOD_KEYPAD, windot11/DOT11_WPS_CONFIG_METHOD_NULL, windot11/DOT11_WPS_CONFIG_METHOD_PUSHBUTTON"
ms.topic: enum
f1_keywords:
 - "windot11/DOT11_WPS_CONFIG_METHOD"
req.header: windot11.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Windot11.h
api_name:
- DOT11_WPS_CONFIG_METHOD
product:
- Windows
targetos: Windows
req.typenames: DOT11_WPS_CONFIG_METHOD, *PDOT11_WPS_CONFIG_METHOD
product:
- Windows 10 or later.
---

# _DOT11_WPS_CONFIG_METHOD enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_WPS_CONFIG_METHOD enumeration specifies the Wi-Fi Protected Setup methods.


## -syntax


```cpp
typedef enum _DOT11_WPS_CONFIG_METHOD {
  DOT11_WPS_CONFIG_METHOD_NULL        = 0,
  DOT11_WPS_CONFIG_METHOD_DISPLAY     = 0x0008,
  DOT11_WPS_CONFIG_METHOD_PUSHBUTTON  = 0x0080,
  DOT11_WPS_CONFIG_METHOD_KEYPAD      = 0x0100
} DOT11_WPS_CONFIG_METHOD;
```


## -enum-fields




### -field DOT11_WPS_CONFIG_METHOD_NULL

No setup method is configured.


### -field DOT11_WPS_CONFIG_METHOD_DISPLAY

Setup is configured by a software user interface.


### -field DOT11_WPS_CONFIG_METHOD_NFC_TAG


### -field DOT11_WPS_CONFIG_METHOD_NFC_INTERFACE


### -field DOT11_WPS_CONFIG_METHOD_PUSHBUTTON

Setup is configured by push button enablement.


### -field DOT11_WPS_CONFIG_METHOD_KEYPAD

Setup is configured by a keypad action.


### -field DOT11_WPS_CONFIG_METHOD_WFDS_DEFAULT



