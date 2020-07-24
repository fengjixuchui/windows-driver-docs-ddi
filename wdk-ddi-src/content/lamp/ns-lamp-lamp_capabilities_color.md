---
UID: NS:lamp.LAMP_CAPABILITIES_COLOR
title: LAMP_CAPABILITIES_COLOR (lamp.h)
description: This structure is the I/O parameter type of IOCTL_LAMP_{GET|SET}_INTENSITY_COLOR.
old-location: stream\lamp_capabilities_color.htm
tech.root: stream
ms.assetid: BCF2171C-93CB-4DAC-AA78-C272D5445F99
ms.date: 04/23/2018
keywords: ["LAMP_CAPABILITIES_COLOR structure"]
ms.keywords: LAMP_CAPABILITIES_COLOR, LAMP_CAPABILITIES_COLOR structure [Streaming Media Devices], lamp/LAMP_CAPABILITIES_COLOR, stream.lamp_capabilities_color
f1_keywords:
 - "lamp/LAMP_CAPABILITIES_COLOR"
 - "LAMP_CAPABILITIES_COLOR"
req.header: lamp.h
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
- lamp.h
api_name:
- LAMP_CAPABILITIES_COLOR
targetos: Windows
req.typenames: LAMP_CAPABILITIES_COLOR
---

# LAMP_CAPABILITIES_COLOR structure


## -description


This structure is the I/O parameter type of <b>IOCTL_LAMP_{GET|SET}_INTENSITY_COLOR</b>.


## -struct-fields




### -field IsSupported

<b>TRUE</b> if the device can emit color light; <b>FALSE</b> otherwise.


### -field IsLightIntensityAdjustable

If <b>IsSupported</b> evaluates to <b>TRUE</b> (the driver is capable of emitting color light) and this field evaluates to <b>TRUE</b>, a client can get/set light intensity of a color lamp by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ni-lamp-ioctl_lamp_get_intensity_color">IOCTL_LAMP_GET_INTENSITY_COLOR</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/lamp/ni-lamp-ioctl_lamp_set_intensity_color">IOCTL_LAMP_SET_INTENSITY_COLOR</a>.


