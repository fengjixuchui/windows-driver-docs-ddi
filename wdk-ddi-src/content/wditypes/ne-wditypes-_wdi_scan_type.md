---
UID: NE:wditypes._WDI_SCAN_TYPE
title: _WDI_SCAN_TYPE (wditypes.h)
description: The WDI_SCAN_TYPE enumeration defines the scan types.
old-location: netvista\wdi_scan_type.htm
tech.root: netvista
ms.assetid: DF4ECD03-2C2F-44B3-82BE-E57B333AF069
ms.date: 05/02/2018
ms.keywords: WDI_SCAN_TYPE, WDI_SCAN_TYPE enumeration [Device and Driver Installation], WDI_SCAN_TYPE_ACTIVE_ONLY, WDI_SCAN_TYPE_AUTO, WDI_SCAN_TYPE_PASSIVE_ONLY, _WDI_SCAN_TYPE, netvista.wdi_scan_type, netvista.wifi_scan_type, wditypes/WDI_SCAN_TYPE, wditypes/WDI_SCAN_TYPE_ACTIVE_ONLY, wditypes/WDI_SCAN_TYPE_AUTO, wditypes/WDI_SCAN_TYPE_PASSIVE_ONLY
ms.topic: enum
f1_keywords:
 - "wditypes/WDI_SCAN_TYPE"
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- wditypes.hpp
api_name:
- WDI_SCAN_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDI_SCAN_TYPE
---

# _WDI_SCAN_TYPE enumeration


## -description


The WDI_SCAN_TYPE enumeration defines the scan types.


## -enum-fields




### -field WDI_SCAN_TYPE_ACTIVE_ONLY

The port should transmit a probe request on the channels that it scans. Even for active scans, the port must follow regulatory restrictions on the channel and must not scan on channels that would need a passive scan.


### -field WDI_SCAN_TYPE_PASSIVE_ONLY

The port should not transmit a probe request on the channels that it scans.


### -field WDI_SCAN_TYPE_AUTO

The port can perform an active or passive can or can use a combination of both scan types. It should prefer using Active scans when possible. This is the default scan type setting.


### -field WDI_SCAN_TYPE_MAX_VALUE



