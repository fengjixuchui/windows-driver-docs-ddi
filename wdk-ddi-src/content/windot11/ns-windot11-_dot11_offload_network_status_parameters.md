---
UID: NS:windot11._DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
title: _DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS (windot11.h)
description: The DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure indicates the success of the discovery of networks in the offload list.
old-location: netvista\dot11_offload_network_status_parameters.htm
tech.root: netvista
ms.assetid: 4A911BFF-5515-4E51-953D-86CECA123DA0
ms.date: 02/16/2018
keywords: ["DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure"]
ms.keywords: "*PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, netvista.dot11_offload_network_status_parameters, windot11/DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, windot11/PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS"
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
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
req.typenames: DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, *PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
f1_keywords:
 - _DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
 - windot11/_DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
 - PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
 - windot11/PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
 - DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
 - windot11/DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS
product:
 - Windows 10 or later.
---

# _DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure


## -description

<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure indicates the success of the discovery of networks in the offload list.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_OFFLOAD_NETWORK_STATUS_PARAMETERS_REVISION_1</td>
</tr>
</table>

### -field Status

This must be STATUS_SUCCESS.

## -syntax

```cpp
typedef struct _DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  NDIS_STATUS        Status;
} DOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS, *PDOT11_OFFLOAD_NETWORK_STATUS_PARAMETERS;
```

