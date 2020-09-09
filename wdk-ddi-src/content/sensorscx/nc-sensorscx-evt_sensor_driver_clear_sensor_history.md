---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_CLEAR_SENSOR_HISTORY
title: EVT_SENSOR_DRIVER_CLEAR_SENSOR_HISTORY (sensorscx.h)
description: Clears the history recorded so far in the sensor.
ms.assetid: f38c9a95-78ec-4839-a57d-14229fb5e297
ms.date: 10/19/2018
keywords: ["EVT_SENSOR_DRIVER_CLEAR_SENSOR_HISTORY callback function"]
req.header: sensorscx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - EVT_SENSOR_DRIVER_CLEAR_SENSOR_HISTORY
 - sensorscx/EVT_SENSOR_DRIVER_CLEAR_SENSOR_HISTORY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - sensorscx.h
api_name:
 - EVT_SENSOR_DRIVER_CLEAR_SENSOR_HISTORY
---

# EVT_SENSOR_DRIVER_CLEAR_SENSOR_HISTORY callback function


## -description

Clears the history recorded so far in the sensor.

## -parameters

### -param Sensor

A reference to the sensor object.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

EVT_SENSOR_DRIVER_CLEAR_SENSOR_HISTORY EvtSensorDriverClearSensorHistory; 

// Definition

NTSTATUS EvtSensorDriverClearSensorHistory 
(
	SENSOROBJECT Sensor
)
{...}

```

