---
UID: NC:d3dkmddi.DXGKDDI_SETPALETTE
title: DXGKDDI_SETPALETTE (d3dkmddi.h)
description: The DxgkDdiSetPalette function programs the color registers for palettized 8 bits-per-pixel (bpp) modes.
old-location: display\dxgkddisetpalette.htm
ms.assetid: 3a46bf84-df62-4247-b842-d5b131c96428
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SETPALETTE, DXGKDDI_SETPALETTE callback, DmFunctions_88e6fd1a-1c14-4a4e-8616-c508b07ed94e.xml, DxgkDdiSetPalette, DxgkDdiSetPalette callback function [Display Devices], d3dkmddi/DxgkDdiSetPalette, display.dxgkddisetpalette
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DxgkDdiSetPalette"
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DxgkDdiSetPalette
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_SETPALETTE callback function


## -description


The <i>DxgkDdiSetPalette</i> function programs the color registers for palettized 8 bits-per-pixel (bpp) modes.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.


### -param pSetPalette [in]

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_dxgkarg_setpalette">DXGKARG_SETPALETTE</a> structure that describes the palette to set for the display. 


## -returns



<i>DxgkDdiSetPalette</i> returns STATUS_SUCCESS, or an appropriate error result if the display palette is not successfully set. 




## -remarks



Implementation of the <i>DxgkDdiSetPalette</i> function in the Windows Vista display driver model replaces <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddvdeo/ni-ntddvdeo-ioctl_video_set_color_registers">IOCTL_VIDEO_SET_COLOR_REGISTERS</a> functionality in the Windows 2000 display driver model.

<i>DxgkDdiSetPalette</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_palettedata">D3DKMDT_PALETTEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_dxgkarg_setpalette">DXGKARG_SETPALETTE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>
 

 

