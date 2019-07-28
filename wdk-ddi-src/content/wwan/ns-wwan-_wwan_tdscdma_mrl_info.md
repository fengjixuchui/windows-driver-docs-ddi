---
UID: NS:wwan._WWAN_TDSCDMA_MRL_INFO
title: _WWAN_TDSCDMA_MRL_INFO (wwan.h)
description: The WWAN_TDSCDMA_MRL_INFO structure represents information about a neighboring TDSCDMA cell.
old-location: netvista\wwan_tdscdma_mrl_info.htm
tech.root: netvista
ms.assetid: 4EA0AE24-E4B0-49E0-8C50-44F6890C5C52
ms.date: 05/02/2018
ms.keywords: "*PWWAN_TDSCDMA_MRL_INFO, PWWAN_TDSCDMA_MRL_INFO, PWWAN_TDSCDMA_MRL_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_TDSCDMA_MRL_INFO, WWAN_TDSCDMA_MRL_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_TDSCDMA_MRL_INFO, netvista.wwan_tdscdma_mrl_info, wwan/PWWAN_TDSCDMA_MRL_INFO, wwan/WWAN_TDSCDMA_MRL_INFO"
ms.topic: struct
f1_keywords:
 - "wwan/WWAN_TDSCDMA_MRL_INFO"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
- wwan.h
api_name:
- WWAN_TDSCDMA_MRL_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_TDSCDMA_MRL_INFO, *PWWAN_TDSCDMA_MRL_INFO
---

# _WWAN_TDSCDMA_MRL_INFO structure


## -description


The <b>WWAN_TDSCDMA_MRL_INFO</b> structure represents information about a neighboring TDSCDMA cell.


## -struct-fields




### -field ProviderIdOffset

The offset in bytes, calculated from the beginning of this structure, to a numeric (0-9) string called <i>ProviderId</i> that represents the network provider identity. This string is a concatenation of a three-digit Mobile Country Code (MCC) and a two or three-digit Mobile Network Code (MNC). This member can be NULL when no <i>ProviderId</i> information is returned.


### -field ProviderIdSize

The size, in bytes, used for <i>ProviderId</i>.


### -field LocationAreaCode

The Location Area Code (0-65535). Use 0xFFFFFFFF when this information is not available.


### -field CellId

The Cell ID (0-268435455). Use 0xFFFFFFFF when this information is not available.


### -field UARFCN

The UTRA Absolute Radio Frequency Channel Number for the serving cell (0-16383). Use 0xFFFFFFFF when this information is not available.


### -field CellParameterId

The Cell Parameter ID (0-127). Use 0xFFFFFFFF when this information is not available.

### -field TimingAdvance

The Timing Advance (0-1023). This member is the same value for all timeslots. Use 0xFFFFFFFF when this information is not available.


### -field RSCP

The Received Signal Code Power of the serving cell. The range is -120 to -25, in units of 1dBm in Q8 L3 filtered. Use 0xFFFFFFFF when this information is not available.


### -field PathLoss

The path loss of the serving cell (46-158). Use 0xFFFFFFFF when this information is not available.


### -field Data

The data buffer containing <i>ProviderId</i>.



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_base_stations_info">WWAN_BASE_STATIONS_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_tdscdma_mrl">WWAN_TDSCDMA_MRL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_tdscdma_serving_cell_info">WWAN_TDSCDMA_SERVING_CELL_INFO</a>
 

 

