---
UID: NS:d3dkmddi._DXGK_RENDERKM_COMMAND
title: _DXGK_RENDERKM_COMMAND (d3dkmddi.h)
description: The DXGK_RENDERKM_COMMAND structure is used to construct a command buffer to control GDI hardware-accelerated rendering.
old-location: display\dxgk_renderkm_command.htm
ms.assetid: 998bf0ca-c08d-41d9-ba3e-74a620ed51ae
ms.date: 05/10/2018
keywords: ["DXGK_RENDERKM_COMMAND structure"]
ms.keywords: DXGK_RENDERKM_COMMAND, DXGK_RENDERKM_COMMAND structure [Display Devices], DmStructs_b23578a5-ae81-42c8-95ce-3ba9b4691d57.xml, _DXGK_RENDERKM_COMMAND, d3dkmddi/DXGK_RENDERKM_COMMAND, display.dxgk_renderkm_command
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
targetos: Windows
tech.root: display
req.typenames: DXGK_RENDERKM_COMMAND
f1_keywords:
 - _DXGK_RENDERKM_COMMAND
 - d3dkmddi/_DXGK_RENDERKM_COMMAND
 - DXGK_RENDERKM_COMMAND
 - d3dkmddi/DXGK_RENDERKM_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_RENDERKM_COMMAND
product:
 - Windows
---

# _DXGK_RENDERKM_COMMAND structure


## -description

The DXGK_RENDERKM_COMMAND structure is used to construct a command buffer to control GDI hardware-accelerated rendering.

## -struct-fields

### -field OpCode

      [in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_renderkm_operation">DXGK_RENDERKM_OPERATION</a>-type operation code that identifies the GDI hardware-accelerated rendering operation to process. For more information about GDI hardware acceleration, see the Remarks section.

### -field CommandSize

      [in] The size of the current command, in bytes. This is equal to the number of bytes from the beginning of DXGK_RENDERKM_COMMAND up to the next command.

### -field Command

### -field BitBlt

       [in] A bit-block transfer (bitblt) that is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_bitblt">DXGK_GDIARG_BITBLT</a> structure.

### -field ColorFill

       [in] A color fill that is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_colorfill">DXGK_GDIARG_COLORFILL</a> structure.

### -field AlphaBlend

       [in] An alpha blend that is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_alphablend">DXGK_GDIARG_ALPHABLEND</a> structure.

### -field StretchBlt

       [in] A stretch bit-block transfer that is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_stretchblt">DXGK_GDIARG_STRETCHBLT</a> structure.

### -field TransparentBlt

       [in] A transparent bit-block transfer that is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_transparentblt">DXGK_GDIARG_TRANSPARENTBLT</a> structure.

### -field ClearTypeBlend

       [in] A ClearType blend that is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_cleartypeblend">DXGK_GDIARG_CLEARTYPEBLEND</a> structure.

## -remarks

An array of variable-size DXGK_RENDERKM_COMMAND structures defines a command buffer that is used to control GDI hardware-accelerated rendering.

A display miniport driver should report that it supports command buffer processing for GDI hardware acceleration by setting <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>-><b>PresentationCaps</b>.<b>SupportKernelModeCommandBuffer</b> to <b>TRUE</b>.

<div class="alert"><b>Note</b>    A display miniport driver should report that it supports GDI hardware acceleration only if the cache-coherent GPU aperture segment exists, and there is no significant performance penalty when the CPU accesses the memory.</div>
<div> </div>
Each command varies in length depending on the value of the <b>OpCode</b> member and the number of sub-rectangles in the command.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_alphablend">DXGK_GDIARG_ALPHABLEND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_bitblt">DXGK_GDIARG_BITBLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_cleartypeblend">DXGK_GDIARG_CLEARTYPEBLEND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_colorfill">DXGK_GDIARG_COLORFILL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_stretchblt">DXGK_GDIARG_STRETCHBLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_transparentblt">DXGK_GDIARG_TRANSPARENTBLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_presentationcaps">DXGK_PRESENTATIONCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_renderkm_operation">DXGK_RENDERKM_OPERATION</a>

