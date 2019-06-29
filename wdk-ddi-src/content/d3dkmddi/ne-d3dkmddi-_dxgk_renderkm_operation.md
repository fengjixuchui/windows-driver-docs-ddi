---
UID: NE:d3dkmddi._DXGK_RENDERKM_OPERATION
title: _DXGK_RENDERKM_OPERATION (d3dkmddi.h)
description: The DXGK_RENDERKM_OPERATION enumeration indicates the type of GDI hardware-accelerated rendering operation to perform when the DxgkDdiRenderKm function is called.
old-location: display\dxgk_renderkm_operation.htm
ms.assetid: bde22894-97a1-42a8-97c1-ba9738c087b9
ms.date: 05/10/2018
ms.keywords: DXGK_GDIOP_ALPHABLEND, DXGK_GDIOP_BITBLT, DXGK_GDIOP_CLEARTYPEBLEND, DXGK_GDIOP_COLORFILL, DXGK_GDIOP_ESCAPE, DXGK_GDIOP_STRETCHBLT, DXGK_GDIOP_TRANSPARENTBLT, DXGK_RENDERKM_OPERATION, DXGK_RENDERKM_OPERATION enumeration [Display Devices], DmEnums_f7b836bc-00ed-4ecc-8bb7-460e3e44d165.xml, _DXGK_RENDERKM_OPERATION, d3dkmddi/DXGK_GDIOP_ALPHABLEND, d3dkmddi/DXGK_GDIOP_BITBLT, d3dkmddi/DXGK_GDIOP_CLEARTYPEBLEND, d3dkmddi/DXGK_GDIOP_COLORFILL, d3dkmddi/DXGK_GDIOP_ESCAPE, d3dkmddi/DXGK_GDIOP_STRETCHBLT, d3dkmddi/DXGK_GDIOP_TRANSPARENTBLT, d3dkmddi/DXGK_RENDERKM_OPERATION, display.dxgk_renderkm_operation
ms.topic: enum
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
- DXGK_RENDERKM_OPERATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_RENDERKM_OPERATION
---

# _DXGK_RENDERKM_OPERATION enumeration


## -description


The DXGK_RENDERKM_OPERATION enumeration indicates the type of GDI hardware-accelerated rendering operation to perform when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a> function is called.


## -enum-fields




### -field DXGK_GDIOP_BITBLT

Indicates a bit-block transfer (bitblt).


### -field DXGK_GDIOP_COLORFILL

Indicates a color fill.


### -field DXGK_GDIOP_ALPHABLEND

Indicates an alpha blend.


### -field DXGK_GDIOP_STRETCHBLT

Indicates a stretch blt.


### -field DXGK_GDIOP_ESCAPE

Reserved for future use. The driver should skip this command when setting the value of the <b>CommandSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_renderkm_command">DXGK_RENDERKM_COMMAND</a> structure.


### -field DXGK_GDIOP_TRANSPARENTBLT

Indicates a blt with transparency.


### -field DXGK_GDIOP_CLEARTYPEBLEND

Indicates a ClearType blend.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_renderkm_command">DXGK_RENDERKM_COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a>
 

 

