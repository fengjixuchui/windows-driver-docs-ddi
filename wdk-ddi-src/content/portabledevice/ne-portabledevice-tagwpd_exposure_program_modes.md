---
UID: NE:portabledevice.tagWPD_EXPOSURE_PROGRAM_MODES
title: WPD_EXPOSURE_PROGRAM_MODES (portabledevice.h)
description: The WPD_EXPOSURE_PROGRAM_MODES enumeration type describes an exposure mode to use when capturing images with a device.
old-location: wpddk\wpd_exposure_program_modes.htm
tech.root: wpd_dk
ms.assetid: 369900fa-af2f-4929-b2cb-937c67e60769
ms.date: 02/15/2018
keywords: ["tagWPD_EXPOSURE_PROGRAM_MODES enumeration"]
ms.keywords: WPD_EXPOSURE_PROGRAM_MODES, WPD_EXPOSURE_PROGRAM_MODES enumeration, WPD_EXPOSURE_PROGRAM_MODE_ACTION, WPD_EXPOSURE_PROGRAM_MODE_APERTURE_PRIORITY, WPD_EXPOSURE_PROGRAM_MODE_AUTO, WPD_EXPOSURE_PROGRAM_MODE_CREATIVE, WPD_EXPOSURE_PROGRAM_MODE_MANUAL, WPD_EXPOSURE_PROGRAM_MODE_PORTRAIT, WPD_EXPOSURE_PROGRAM_MODE_SHUTTER_PRIORITY, WPD_EXPOSURE_PROGRAM_MODE_UNDEFINED, enumeration, portabledevice/WPD_EXPOSURE_PROGRAM_MODES, portabledevice/WPD_EXPOSURE_PROGRAM_MODE_ACTION, portabledevice/WPD_EXPOSURE_PROGRAM_MODE_APERTURE_PRIORITY, portabledevice/WPD_EXPOSURE_PROGRAM_MODE_AUTO, portabledevice/WPD_EXPOSURE_PROGRAM_MODE_CREATIVE, portabledevice/WPD_EXPOSURE_PROGRAM_MODE_MANUAL, portabledevice/WPD_EXPOSURE_PROGRAM_MODE_PORTRAIT, portabledevice/WPD_EXPOSURE_PROGRAM_MODE_SHUTTER_PRIORITY, portabledevice/WPD_EXPOSURE_PROGRAM_MODE_UNDEFINED, tagWPD_EXPOSURE_PROGRAM_MODES, wpddk.wpd_exposure_program_modes
f1_keywords:
 - "portabledevice/WPD_EXPOSURE_PROGRAM_MODES"
 - "WPD_EXPOSURE_PROGRAM_MODES"
req.header: portabledevice.h
req.include-header: 
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- PortableDevice.h
api_name:
- WPD_EXPOSURE_PROGRAM_MODES
targetos: Windows
req.typenames: WPD_EXPOSURE_PROGRAM_MODES
ms.custom: RS5
---

# tagWPD_EXPOSURE_PROGRAM_MODES enumeration


## -description



The <b>WPD_EXPOSURE_PROGRAM_MODES</b> enumeration type describes an exposure mode to use when capturing images with a device.




## -enum-fields




### -field WPD_EXPOSURE_PROGRAM_MODE_UNDEFINED

The exposure mode has not been specified.


### -field WPD_EXPOSURE_PROGRAM_MODE_MANUAL

The application should specify all exposure settings.


### -field WPD_EXPOSURE_PROGRAM_MODE_AUTO

Use a device-defined automatic exposure mode.


### -field WPD_EXPOSURE_PROGRAM_MODE_APERTURE_PRIORITY

An automated exposure mode that indicates that the lens aperture value should remain fixed, but shutter speed should be determined by the device.


### -field WPD_EXPOSURE_PROGRAM_MODE_SHUTTER_PRIORITY

An automated exposure mode that indicates that the shutter speed should remain fixed, but that lens aperture should be determined by the device.


### -field WPD_EXPOSURE_PROGRAM_MODE_CREATIVE

An automated exposure mode that tries to maximize the depth of field.


### -field WPD_EXPOSURE_PROGRAM_MODE_ACTION

An automated exposure mode that tries to maximize the shutter speed.


### -field WPD_EXPOSURE_PROGRAM_MODE_PORTRAIT

An automated exposure mode that specifies a relatively shallow depth of field.


## -remarks



Indicates the exposure program mode of the device. This enumeration is used by the <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_EXPOSURE_PROGRAM_MODE</a> property.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>
 

 

