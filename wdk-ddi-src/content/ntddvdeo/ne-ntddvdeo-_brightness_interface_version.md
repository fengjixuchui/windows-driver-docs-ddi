---
UID: NE:ntddvdeo._BRIGHTNESS_INTERFACE_VERSION
title: _BRIGHTNESS_INTERFACE_VERSION (ntddvdeo.h)
description: Specifies the brightness interface versions.
ms.assetid: 2d13834a-bed3-4906-9a5c-778864173641
ms.date: 10/19/2018
keywords: ["_BRIGHTNESS_INTERFACE_VERSION enumeration"]
f1_keywords:
 - "ntddvdeo/_BRIGHTNESS_INTERFACE_VERSION"
 - "_BRIGHTNESS_INTERFACE_VERSION"
ms.keywords: _BRIGHTNESS_INTERFACE_VERSION, BRIGHTNESS_INTERFACE_VERSION,
req.header: ntddvdeo.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: BRIGHTNESS_INTERFACE_VERSION
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- ntddvdeo.h
api_name:
- _BRIGHTNESS_INTERFACE_VERSION
product: 
- Windows
targetos: Windows
tech.root: display
---

# _BRIGHTNESS_INTERFACE_VERSION enumeration

## -description

Specifies the brightness interface versions.

## -enum-fields

### -field BRIGHTNESS_INTERFACE_VERSION_1

Supports brightness control in integrated display panels.

### -field BRIGHTNESS_INTERFACE_VERSION_2

Lets a display miniport driver reduce power to the display backlight and still smoothly adapt to changes in ambient light and user requests to change brightness. Starting with Windows 8, if the system includes an ambient light sensor, the driver must support the Brightness Control Interface V 2.

### -field BRIGHTNESS_INTERFACE_VERSION_3

Supports multiple displays that can be set to calibrated nit-based brightness levels.

