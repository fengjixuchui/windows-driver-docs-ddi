---
UID: NS:d3dkmddi._DXGK_GDIARG_CLEARTYPEBLEND
title: _DXGK_GDIARG_CLEARTYPEBLEND (d3dkmddi.h)
description: The DXGK_GDIARG_CLEARTYPEBLEND structure describes the characteristics of a GDI hardware-accelerated ClearType and antialiased text pixel blending operation.
old-location: display\dxgk_gdiarg_cleartypeblend.htm
ms.assetid: 1e67bb33-c2e5-4f3c-9ea6-feeb4a1fe645
ms.date: 05/10/2018
ms.keywords: DXGK_GDIARG_CLEARTYPEBLEND, DXGK_GDIARG_CLEARTYPEBLEND structure [Display Devices], DmStructs_b59789df-1494-45ea-b89a-4403e6c82dfd.xml, _DXGK_GDIARG_CLEARTYPEBLEND, d3dkmddi/DXGK_GDIARG_CLEARTYPEBLEND, display.dxgk_gdiarg_cleartypeblend
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_GDIARG_CLEARTYPEBLEND"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
- DXGK_GDIARG_CLEARTYPEBLEND
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_GDIARG_CLEARTYPEBLEND
---

# _DXGK_GDIARG_CLEARTYPEBLEND structure


## -description


The DXGK_GDIARG_CLEARTYPEBLEND structure describes the characteristics of a GDI hardware-accelerated ClearType and antialiased text pixel blending operation.


## -struct-fields




### -field DstRect

[in] A <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure that defines the rectangular area to be modified. This rectangle is specified in the coordinate system of the destination surface and is defined by two points: upper left and lower right. The rectangle is lower-right exclusive; that is, its lower and right edges are not a part of the bit-block transfer. The two points that define the rectangle are always well ordered. 

The destination rectangle defined by <b>DstRect</b> can exceed the bounds of the destination surface, but sub-rectangles cannot. Additionally, all sub-rectangles are guaranteed to fit inside the destination surface. Sub-rectangles can be constrained further by a bounding rectangle that is smaller than the destination rectangle.


### -field TmpSurfAllocationIndex


      [in] An index of the element in the allocation list that specifies a temporary surface. This surface can be used to read the destination before executing a pixel shader.
     


### -field GammaSurfAllocationIndex


      [in] An index of the element in the allocation list that specifies a gamma table of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ne-d3dkmdt-_d3dkmdt_gdisurfacetype">D3DKMDT_GDISURFACETYPE</a>. The format of the gamma lookup allocation is 8 bits per pixel, and the resolution is 512 x 16 pixels. Each row of the allocation contains two tables: gamma and inverse gamma. Each table has 256 entries.
     


### -field AlphaSurfAllocationIndex


      [in] An index of the element in the allocation list that specifies alpha values of a surface. The alpha surface is in the same coordinate space as the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     


### -field DstAllocationIndex


      [in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>DstRect</b> destination rectangle.
     


### -field DstToAlphaOffsetX


      [in] An offset in the x direction that transforms the destination rectangle coordinate space to the alpha surface coordinate space.
     


### -field DstToAlphaOffsetY


      [in] An offset in the y direction that transforms the destination rectangle coordinate space to the alpha surface coordinate space.
     


### -field Color


      [in] The foreground color, in 32-bit ARGB unsigned pixel format (as defined by the D3DDDIFMT_A8R8G8B8 value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a> enumeration), corrected for gamma.
     


### -field Gamma


      [in] An index of the element in the allocation list that specifies the gamma lookup table. Gamma values are in the range of [0, 15], otherwise gamma is 0xFFFFFFFF (the value of D3DKM_INVALID_GAMMA_INDEX). See Remarks for more information on how gamma is used in ClearType blending.
     


### -field NumSubRects


      The number of sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     


### -field pSubRects


      A pointer to the sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     


### -field AlphaSurfPitch


      The pitch, in bytes, of the alpha surface referenced by <b>AlphaSurfAllocationIndex</b>.
     


### -field Color2


      [in] The foreground color, in 32-bit ARGB unsigned pixel format (as defined by the D3DDDIFMT_A8R8G8B8 value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a> enumeration), not corrected for gamma.
     


## -remarks



The value of <b>Gamma</b> should be in the range of [0, 15] unless set to 0xFFFFFFFF (the value of D3DKM_INVALID_GAMMA_INDEX). The value of <b>Gamma</b> is the index of a row in the gamma allocation.

When gamma is in the range of [0, 15], the following per-pixel blending is performed.

```cpp
GammaTable = (BYTE*)GammaSurfaceAddress + Gamma * GammaSurfacePitch;
InverseGammaTable = (BYTE*)GammaSurfaceAddress + Gamma * GammaSurfacePitch + 256;

Tmp.r = GammaTable[D.r]; // red
Tmp.g = GammaTable[D.g]; // green
Tmp.b = GammaTable[D.b]; // blue

BlendColor.r = InverseGammaTable[round((Tmp.r + (Color.r - Tmp.r) * A.r / 255.0))]
BlendColor.g = InverseGammaTable[round((Tmp.g + (Color.g - Tmp.g) * A.g / 255.0))]
BlendColor.b = InverseGammaTable[round((Tmp.b + (Color.b - Tmp.b) * A.b / 255.0))]
OutputColor.a = D.a

OutputColor.r = (A.r == 0) ? D.r : (A.r == 255) ? Color2.r : BlendColor.r;
OutputColor.g = (A.g == 0) ? D.g : (A.g == 255) ? Color2.g : BlendColor.g;
OutputColor.b = (A.b == 0) ? D.b : (A.b == 255) ? Color2.b : BlendColor.b;
```

When gamma is equal to 0xFFFFFFFF (the value of D3DKM_INVALID_GAMMA_INDEX), the following per-pixel blending is performed.

```
OutputColor.a = D.a
OutputColor.r = D.r + (Color.r - D.r) * (Color.r >= D.r ? A.r : A.g) / 255.0
OutputColor.g = D.g + (Color.g - D.g) * (Color.g >= D.g ? A.r : A.g) / 255.0
OutputColor.b = D.b + (Color.b - D.b) * (Color.b >= D.b ? A.r : A.g) / 255.0
```

Where the following parameters are in the D3DDDIFMT_A8R8G8B8 format defined in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a> enumeration:

<ul>
<li>
<b>Color</b> = gamma-corrected foreground color, as defined by the <b>Color</b> member

</li>
<li>
<b>Color2</b> = foreground color, not gamma corrected, as defined by the <b>Color2</b> member

</li>
<li>
D = destination pixel color

</li>
<li>
A = alpha surface color

</li>
</ul>
The display miniport driver must ensure that when a component of A is zero, the corresponding output component is the same as the background color component (D).

The driver must also ensure that when a component of A is 0xFF, the corresponding output component is the same as the foreground color component (<b>Color2</b>).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ne-d3dkmdt-_d3dkmdt_gdisurfacetype">D3DKMDT_GDISURFACETYPE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>
 

 

