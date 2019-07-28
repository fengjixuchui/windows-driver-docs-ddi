---
UID: NS:d3dkmddi._DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
title: _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 (d3dkmddi.h)
description: Contains arguments for the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3 function.
old-location: display\dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3.htm
ms.assetid: 1C6324DB-18E2-4CBC-9589-73DF3EB79503
ms.date: 05/10/2018
ms.keywords: "*IN_OUT_PDXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 structure [Display Devices], _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, d3dkmddi/DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, display.dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3"
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3"
req.header: d3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
---

# _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 structure


## -description


Contains arguments for the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3 function.


## -struct-fields




### -field VidPnSourceId

An integer that identifies a video present source on the display adapter.


### -field InputFlags

A DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS structure that identifies the type of display operation to perform.


### -field OutputFlags

A DXGK_SETVIPNSOURCEADDRESS_OUTPUT_FLAGS structure that returns information from the driver.


### -field PlaneCount

The number of overlay planes in the ppPlanes list.


### -field ppPlanes

An array of pointers to a DXGK_MULTIPLANE_OVERLAY_PLANE3 structures that specify the overlay planes to display.


### -field pPostComposition

Pointer to a DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION structure containing virtual mode information and other transform information that should be applied after the planes have been composed.

If NULL, no post composition transforms should be applied.


### -field Duration

The length of time, in units of 100 nanoseconds, between when the current present operation flips to the screen and the next vertical blanking interrupt occurs.

If zero, the refresh rate should be the default rate based on the current mode.


### -field pHDRMetaData

Pointer to a DXGK_HDR_METADATA structure indicating any metadata information that might be available. A NULL value indicates that no new metadata is available.

