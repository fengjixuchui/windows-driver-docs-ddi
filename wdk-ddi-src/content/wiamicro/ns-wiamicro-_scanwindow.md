---
UID: NS:wiamicro._SCANWINDOW
title: _SCANWINDOW (wiamicro.h)
description: The SCANWINDOW structure is used by the WIA Flatbed driver to tell the microdriver what image area to scan.
old-location: image\scanwindow.htm
tech.root: image
ms.assetid: c4b507ac-af32-4949-add0-e19c00e328fe
ms.date: 05/03/2018
keywords: ["SCANWINDOW structure"]
ms.keywords: "*PSCANWINDOW, MicroDrv_b89f7f9d-a1e6-4a61-83e3-659c6f3a9d13.xml, PSCANWINDOW, PSCANWINDOW structure pointer [Imaging Devices], SCANWINDOW, SCANWINDOW structure [Imaging Devices], _SCANWINDOW, image.scanwindow, wiamicro/PSCANWINDOW, wiamicro/SCANWINDOW"
req.header: wiamicro.h
req.include-header: Wiamicro.h
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
req.typenames: SCANWINDOW, *PSCANWINDOW
f1_keywords:
 - _SCANWINDOW
 - wiamicro/_SCANWINDOW
 - PSCANWINDOW
 - wiamicro/PSCANWINDOW
 - SCANWINDOW
 - wiamicro/SCANWINDOW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiamicro.h
api_name:
 - SCANWINDOW
---

# _SCANWINDOW structure


## -description

The SCANWINDOW structure is used by the WIA Flatbed driver to tell the microdriver what image area to scan.

## -struct-fields

### -field xPos

Specifies the horizontal position of the left edge of the scan window in pixels.

### -field yPos

Specifies the vertical position of the top edge of the scan window in pixels.

### -field xExtent

Specifies the width of the scan window in pixels.

### -field yExtent

Specifies the height of the scan window in pixels.

