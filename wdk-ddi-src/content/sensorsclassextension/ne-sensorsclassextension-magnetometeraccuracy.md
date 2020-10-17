---
UID: NE:sensorsclassextension.MagnetometerAccuracy
title: MagnetometerAccuracy (sensorsclassextension.h)
description: Specifies the accuracy of the magnetometer.
old-location: sensors\magnetometeraccuracy.htm
tech.root: sensors
ms.assetid: DC495EFB-3522-4220-87F8-3DB501831D6E
ms.date: 05/03/2018
keywords: ["MagnetometerAccuracy enumeration"]
ms.keywords: Approximate, High, MagnetometerAccuracy, MagnetometerAccuracy enumeration [Sensor Devices], Unknown, Unreliable, sensors.magnetometeraccuracy, sensorsclassextension/Approximate, sensorsclassextension/High, sensorsclassextension/MagnetometerAccuracy, sensorsclassextension/Unknown, sensorsclassextension/Unreliable
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,Available in Windows 8.1.
req.target-min-winversvr: None supported
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
req.typenames: MagnetometerAccuracy
f1_keywords:
 - MagnetometerAccuracy
 - sensorsclassextension/MagnetometerAccuracy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - SensorsClassExtension.h
api_name:
 - MagnetometerAccuracy
---

# MagnetometerAccuracy enumeration


## -description

Specifies the accuracy of the magnetometer.

## -enum-fields

### -field MAGNETOMETER_ACCURACY_UNKNOWN

### -field MAGNETOMETER_ACCURACY_UNRELIABLE

### -field MAGNETOMETER_ACCURACY_APPROXIMATE

### -field MAGNETOMETER_ACCURACY_HIGH

#### - Approximate

          The actual and reported values differ but may be accurate enough for some applications. Apps that only need a relative value, like a virtual reality app, can continue without additional calibration.


#### - High

          The actual and reported values are accurate. No additional calibration is needed.


#### - Unknown

The accuracy is currently not available, typically because the driver can't report it.


#### - Unreliable

The reported values have a high degree of inaccuracy. Apps should always ask the user to calibrate the device whenever this value is returned.

## -remarks

Device drivers that support magnetometer accuracy should only report the <b>Unreliable</b>, <b>Approximate</b>, and <b>High</b> values.

Apps that need calibration may periodically ask the user to calibrate the device. We suggest doing this once every 10 minutes.

## -see-also

<a href="/windows-hardware/drivers/sensors/sensor-properties2">Sensor Properties</a>