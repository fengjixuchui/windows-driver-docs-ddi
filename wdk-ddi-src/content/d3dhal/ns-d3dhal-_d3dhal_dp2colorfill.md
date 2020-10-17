---
UID: NS:d3dhal._D3DHAL_DP2COLORFILL
title: _D3DHAL_DP2COLORFILL (d3dhal.h)
description: DirectX 9.0 and later versions only. D3DHAL_DP2COLORFILL is used for color-fill operations when D3dDrawPrimitives2 responds to the D3DDP2OP_COLORFILL command token.
old-location: display\d3dhal_dp2colorfill.htm
tech.root: display
ms.assetid: 6cec8639-1d5e-4b24-8e02-a7ae62740fea
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2COLORFILL structure"]
ms.keywords: "*LPD3DHAL_DP2COLORFILL, D3DHAL_DP2COLORFILL, D3DHAL_DP2COLORFILL structure [Display Devices], LPD3DHAL_DP2COLORFILL, LPD3DHAL_DP2COLORFILL structure pointer [Display Devices], _D3DHAL_DP2COLORFILL, d3dhal/D3DHAL_DP2COLORFILL, d3dhal/LPD3DHAL_DP2COLORFILL, d3dstrct_41b1733a-0f94-4e04-9f7d-dac688c2bc56.xml, display.d3dhal_dp2colorfill"
req.header: d3dhal.h
req.include-header: D3dhal.h
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
req.typenames: D3DHAL_DP2COLORFILL
f1_keywords:
 - _D3DHAL_DP2COLORFILL
 - d3dhal/_D3DHAL_DP2COLORFILL
 - D3DHAL_DP2COLORFILL
 - d3dhal/D3DHAL_DP2COLORFILL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_DP2COLORFILL
---

# _D3DHAL_DP2COLORFILL structure


## -description

   DirectX 9.0 and later versions only.
   

D3DHAL_DP2COLORFILL is used for color-fill operations when <a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> responds to the D3DDP2OP_COLORFILL command token.

## -struct-fields

### -field dwSurface

Specifies the handle to the surface to be filled.

### -field rRect

Specifies a RECTL structure that specifies the upper left and lower right points of a rectangle on the surface to be filled.

### -field Color

Specifies a D3DCOLOR for the color type.

## -remarks

Because DirectX 9.0 and later drivers are required to support the D3DDP2OP_COLORFILL command token, they are not required to expose a capability bit that indicates such support. 

Display drivers must convert input color values for the ARGB and YUV classes of color formats. For color-fill operations, input color values are specified in the <b>Color</b> member. For more information, see <a href="/windows-hardware/drivers/display/handling-color-values-for-pixel-formats">Handling Color Values for Pixel Formats</a>.

When the runtime calls a driver's <b>DdBlt</b> function to perform a color-fill operation, the runtime converts the D3DCOLOR value to an explicit pixel value if the runtime supports the format of that D3DCOLOR value. If the runtime does not support the format, the D3DCOLOR value is passed directly to the driver. 

For more information about D3DCOLOR, see the DirectX SDK documentation.

## -see-also

D3DDP2OP_COLORFILL



<a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>



<a href="/windows/win32/api/ddrawint/nc-ddrawint-pdd_surfcb_blt">DdBlt</a>