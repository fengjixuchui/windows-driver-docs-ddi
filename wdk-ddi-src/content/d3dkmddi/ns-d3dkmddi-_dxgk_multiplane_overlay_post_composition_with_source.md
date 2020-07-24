---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE
title: _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE (d3dkmddi.h)
description: Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check details on hardware support for post composition transform support.
old-location: display\dxgk_multiplane_overlay_post_composition_with_source.htm
ms.assetid: F997E3DB-630D-41C8-B659-36376E05A6B7
ms.date: 05/10/2018
keywords: ["_DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE, DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE, display.dxgk_multiplane_overlay_post_composition_with_source
f1_keywords:
 - "d3dkmddi/DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE"
 - "DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE"
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
- DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE
---

# _DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE structure


## -description


Used in a call to the <b>DxgkDdiCheckMultiPlaneOverlaySupport3 </b>function to check details on hardware support for post composition transform support.


## -struct-fields




### -field VidPnSourceId

The zero-based video present network (VidPN) source identification number of the input for which the support levels are queried.


### -field PostComposition

A DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION structure that specifies additional transforms that should be applied after the planes are composed.

