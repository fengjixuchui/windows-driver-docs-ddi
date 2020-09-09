---
UID: NE:portabledevice.tagWPD_EFFECT_MODES
title: WPD_EFFECT_MODES (portabledevice.h)
description: The WPD_EFFECT_MODES enumeration type describes various visual effects that can be applied to an image.
old-location: wpddk\wpd_effect_modes.htm
tech.root: wpd_dk
ms.assetid: 60789d63-ff36-4085-a1d7-a805c271a385
ms.date: 02/15/2018
keywords: ["tagWPD_EFFECT_MODES enumeration"]
ms.keywords: WPD_EFFECT_MODES, WPD_EFFECT_MODES enumeration, WPD_EFFECT_MODE_BLACK_AND_WHITE, WPD_EFFECT_MODE_COLOR, WPD_EFFECT_MODE_SEPIA, WPD_EFFECT_MODE_UNDEFINED, enumeration, portabledevice/WPD_EFFECT_MODES, portabledevice/WPD_EFFECT_MODE_BLACK_AND_WHITE, portabledevice/WPD_EFFECT_MODE_COLOR, portabledevice/WPD_EFFECT_MODE_SEPIA, portabledevice/WPD_EFFECT_MODE_UNDEFINED, tagWPD_EFFECT_MODES, wpddk.wpd_effect_modes
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
targetos: Windows
req.typenames: WPD_EFFECT_MODES
ms.custom: RS5
f1_keywords:
 - tagWPD_EFFECT_MODES
 - portabledevice/tagWPD_EFFECT_MODES
 - WPD_EFFECT_MODES
 - portabledevice/WPD_EFFECT_MODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PortableDevice.h
api_name:
 - WPD_EFFECT_MODES
---

# tagWPD_EFFECT_MODES enumeration


## -description

The <b>WPD_EFFECT_MODES</b> enumeration type describes various visual effects that can be applied to an image.

## -enum-fields

### -field WPD_EFFECT_MODE_UNDEFINED

No effect has been specified.

### -field WPD_EFFECT_MODE_COLOR

The image should be color.

### -field WPD_EFFECT_MODE_BLACK_AND_WHITE

The image should be black and white.

### -field WPD_EFFECT_MODE_SEPIA

The image should be sepia.

## -remarks

This enumeration is used by the <a href="https://docs.microsoft.com/windows/desktop/wpd_sdk/still-image-properties">WPD_STILL_IMAGE_EFFECT_MODE</a> property.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>

