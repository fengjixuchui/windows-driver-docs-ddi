---
UID: NS:lamp.LAMP_CAPABILITIES_WHITE
title: LAMP_CAPABILITIES_WHITE (lamp.h)
description: This structure is the I/O parameter type of IOCTL_LAMP_{GET|SET}_INTENSITY_WHITE.
old-location: stream\lamp_capabilities_white.htm
tech.root: stream
ms.assetid: F407B953-8B03-4053-A5F4-3E96E9F9645E
ms.date: 04/23/2018
keywords: ["LAMP_CAPABILITIES_WHITE structure"]
ms.keywords: LAMP_CAPABILITIES_WHITE, LAMP_CAPABILITIES_WHITE structure [Streaming Media Devices], lamp/LAMP_CAPABILITIES_WHITE, stream.lamp_capabilities_white
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
targetos: Windows
req.typenames: LAMP_CAPABILITIES_WHITE
f1_keywords:
 - LAMP_CAPABILITIES_WHITE
 - lamp/LAMP_CAPABILITIES_WHITE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - lamp.h
api_name:
 - LAMP_CAPABILITIES_WHITE
---

# LAMP_CAPABILITIES_WHITE structure


## -description

This structure is the I/O parameter type of <b>IOCTL_LAMP_{GET|SET}_INTENSITY_WHITE</b>.

## -struct-fields

### -field IsLightIntensityAdjustable

If this field evaluates <b>TRUE</b>, a client can get/set light intensity by calling <a href="/windows-hardware/drivers/ddi/lamp/ni-lamp-ioctl_lamp_get_intensity_white">IOCTL_LAMP_GET_INTENSITY_WHITE</a>  and <a href="/windows-hardware/drivers/ddi/lamp/ni-lamp-ioctl_lamp_set_intensity_white">IOCTL_LAMP_SET_INTENSITY_WHITE</a>.