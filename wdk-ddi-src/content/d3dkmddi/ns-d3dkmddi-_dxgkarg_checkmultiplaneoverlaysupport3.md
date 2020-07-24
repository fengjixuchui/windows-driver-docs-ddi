---
UID: NS:d3dkmddi._DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3
title: _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3 (d3dkmddi.h)
description: Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check details on hardware support for multi-plane overlays.
old-location: display\dxgkarg_checkmultiplaneoverlaysupport3.htm

ms.assetid: 21FE4E54-5B7D-4068-AC83-A7AFFA739169
ms.date: 04/16/2018
keywords: ["_DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3 structure"]
ms.keywords: "*IN_OUT_PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3 structure, _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3, d3dkmddi/DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3, display.dxgkarg_checkmultiplaneoverlaysupport3"
f1_keywords:
 - "d3dkmddi/DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3"
 - "DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3"
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
- DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3
targetos: Windows
tech.root: display
req.typenames: DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3
---

# _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3 structure


## -description


Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check details on hardware support for multi-plane overlays.


## -struct-fields




### -field PlaneCount

The number of input planes to be enabled.


### -field ppPlanes

An array of pointers pointing to a DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE3 structure that specifies support attributes that the hardware provides for multi-plane overlays.


### -field PostCompositionCount

The number of VidPnSources for which we want to apply post composition transforms.


### -field ppPostComposition

An array of pointers pointing to a DXGK_CHECK_MULTIPLANE_OVERLAY_POST_COMPSOTION_WITH_SOURCE structure that specifies transforms that should be applied after the planes are composed.


### -field Supported

TRUE if the multi-plane overlay configuration can be supported, otherwise FALSE.


### -field ReturnInfo

Specifies additional information.

