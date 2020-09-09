---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3
title: _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3 (d3dkmddi.h)
description: A structure containing the attributes used for the image in a multiplane overlay.
old-location: display\dxgk_multiplane_overlay_attributes3.htm
ms.assetid: 0491AF42-53DF-4538-BE8A-AA5AA7B2C65E
ms.date: 05/10/2018
keywords: ["DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3 structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3, DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3, display.dxgk_multiplane_overlay_attributes3
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1803
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
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3
ms.custom: 19H1
f1_keywords:
 - _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3
 - d3dkmddi/_DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3
 - DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3
 - d3dkmddi/DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3
dev_langs:
 - c++
---

# _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3 structure


## -description

A structure containing the attributes used for the image in a multiplane overlay.

## -struct-fields

### -field Flags

Specifies a combination of flip operations by Oring values in the [DXGK_MULTIPLANE_OVERLAY_FLAGS](ns-d3dkmddi-_dxgk_multiplane_overlay_flags.md) enumeration.

### -field SrcRect

Specifies the source rectangle, of type RECT, relative to the source resource.

### -field DstRect

Specifies the destination rectangle, of type RECT, relative to the monitor resolution.

### -field ClipRect

Specifies additional clipping information, of type RECT, relative to the DstRect rectangle, after the data has been stretched according to the values of SrcRect and DstRect.

The driver and hardware can use the ClipRect member to apply a common stretch factor as the clipping changes when an app occludes part of the DstRect destination rectangle.

### -field Rotation

Specifies the clockwise rotation of the overlay plane, given as a value from the D3DDDI_ROTATION enumeration.

### -field Blend

Specifies the blend mode that applies to this overlay plane and the plane beneath it, given as a value from the [DXGK_MULTIPLANE_OVERLAY_BLEND](ns-d3dkmddi-_dxgk_multiplane_overlay_blend.md) enumeration.

### -field ColorSpaceType

Specifies the color space configuration, given as a value from the [D3DDDI_COLOR_SPACE_TYPE](../d3dukmdt/ne-d3dukmdt-d3dddi_color_space_type.md) enumeration.

### -field StretchQuality

Specifies the overlay plane's stretch quality, given as a value from the [DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY](ne-d3dkmddi-_dxgk_multiplane_overlay_stretch_quality.md) enumeration.

### -field SDRWhiteLevel

Specifies the value in nits that the driver should to map sRGB 1.0.

For HDR content, this will always be 0.

For SDR (standard dynamic range) content, a value of 0 indicates that the driver should map sRGB 1.0 to the default value, which is 80 nits.

This value is ignored when not in HDR mode.

### -field DirtyRectCnt

The number of dirty rectangles of *pDirtyRects*.

### -field pDirtyRects

Pointer of the dirty rectangles.

## -remarks

WDDM 2.3 drivers need to check the SDRWhiteLevel value passed in the [CheckMultiPlaneOverlaySupport3](nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport3.md) callback, and return unsupported if the hardware is unable to adjust the relative brightness of the SDR content.

When boosting the SDR content to the SDRWhiteLevel, the scaling must occur in linear space.

