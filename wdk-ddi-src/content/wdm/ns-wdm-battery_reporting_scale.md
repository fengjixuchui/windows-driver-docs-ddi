---
UID: NS:wdm.__unnamed_struct_2
title: BATTERY_REPORTING_SCALE (wdm.h)
description: Battery miniclass drivers fill in this structure in response to certain BatteryMiniQueryInformation requests.
old-location: battery\battery_reporting_scale.htm
tech.root: battery
ms.assetid: aea1d82d-39b8-4535-a5c3-fb987be1e43c
ms.date: 02/15/2018
keywords: ["BATTERY_REPORTING_SCALE structure"]
ms.keywords: "*PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE structure [Battery Devices], PBATTERY_REPORTING_SCALE, PBATTERY_REPORTING_SCALE structure pointer [Battery Devices], bat-struct_6ecc4955-56b0-4c92-9ce2-46bcd7d6b273.xml, battery.battery_reporting_scale, ntpoapi/BATTERY_REPORTING_SCALE, ntpoapi/PBATTERY_REPORTING_SCALE"
req.header: wdm.h
req.include-header: Batclass.h, Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
req.product: Windows 10 or later.
f1_keywords:
 - PBATTERY_REPORTING_SCALE
 - wdm/PBATTERY_REPORTING_SCALE
 - BATTERY_REPORTING_SCALE
 - wdm/BATTERY_REPORTING_SCALE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntpoapi.h
api_name:
 - BATTERY_REPORTING_SCALE
---

# BATTERY_REPORTING_SCALE structure


## -description

Battery miniclass drivers fill in this structure in response to certain <a href="https://docs.microsoft.com/windows/desktop/api/batclass/nc-batclass-bclass_query_information_callback">BatteryMiniQueryInformation</a> requests.

## -struct-fields

### -field Granularity

Specify the granularity of the <b>Capacity</b> value, in milliwatt-hours. For most batteries, this value describes a monotonically increasing scale of capacity. For lithium-ion batteries, this value describes one of two possible scales: a gross measure of battery capacity, with a large granularity, or a finer measure as the capacity approaches zero.

### -field Capacity

Specify the battery capacity described by the corresponding granularity, in milliwatt-hours.

## -syntax

```cpp
typedef struct {
  ULONG Granularity;
  ULONG Capacity;
} BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE;
```

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/batclass/nc-batclass-bclass_query_information_callback">BatteryMiniQueryInformation</a>

