---
UID: NS:d3dhal._D3DHAL_DP2CLEAR
title: _D3DHAL_DP2CLEAR (d3dhal.h)
description: D3DHAL_DP2CLEAR contains all of the information that the driver needs to perform hardware-assisted clearing on the rendering target, depth buffer or stencil buffer.
old-location: display\d3dhal_dp2clear.htm
tech.root: display
ms.assetid: 8cd81cae-8d6b-48d8-afdc-87e3a81653f4
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2CLEAR structure"]
ms.keywords: "*LPD3DHAL_DP2CLEAR, D3DHAL_DP2CLEAR, D3DHAL_DP2CLEAR structure [Display Devices], LPD3DHAL_DP2CLEAR, LPD3DHAL_DP2CLEAR structure pointer [Display Devices], _D3DHAL_DP2CLEAR, d3dhal/D3DHAL_DP2CLEAR, d3dhal/LPD3DHAL_DP2CLEAR, d3dstrct_2caf8fa1-61b4-4659-af20-a72d6b36173a.xml, display.d3dhal_dp2clear"
f1_keywords:
 - "d3dhal/D3DHAL_DP2CLEAR"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_DP2CLEAR
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2CLEAR
---

# _D3DHAL_DP2CLEAR structure


## -description


D3DHAL_DP2CLEAR contains all of the information that the driver needs to perform hardware-assisted clearing on the rendering target, depth buffer or stencil buffer.


## -struct-fields




### -field dwFlags

Specifies what buffers the driver should clear. This member can be a bitwise OR of the following values:

| **Value** | **Meaning** | 
|:--|:--|
| D3DCLEAR_TARGET | The driver should clear the context's render target to the color specified by the dwFillColor member. | 
| D3DCLEAR_STENCIL | The driver should clear the context's stencil buffer to the value specified by the dwFillStencil member. | 
| D3DCLEAR_ZBUFFER | The driver should clear the context's depth buffer to the depth specified by the dwFillDepth member. | 
| D3DCLEAR_COMPUTERECTS | DirectX 8.0 and later versions only.<br/>If this flag is set, the specified rectangles should be clipped against the current viewport. Furthermore, it is possible that when D3DCLEAR_COMPUTERECTS is specified the number of rectangles to clear can be zero (the number of rectangles to clear can be found in the wStateCount/wPrimtiveCount union of the [D3DHAL_DP2COMMAND](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command)  structure for the clear). In this case the entire viewport should be cleared. | 

 


### -field dwFillColor

Specifies the color that the driver should clear the context's render target to.


### -field dvFillDepth

Specifies the value that the driver should use to set the depth in the context's depth buffer. This member can be a value in the interval 0.0 to 1.0. The driver should convert this value to an integer using the <b>dwZBitMask</b> member of the depth buffer's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ddpixelformat">DDPIXELFORMAT</a> structure.


### -field dwFillStencil

Specifies the value that the driver should clear the context's stencil buffer to. This member can be an integer in the interval 0 to 2ⁿ-1, where <i>n</i> is the number of bits in the stencil buffer.


### -field Rects

Specifies the rectangular areas of the buffer that the driver should clear. The rectangles are specified in screen coordinates. This member of the structure contains the first rectangle area to be blitted. The <b>wStateCount</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> contains the total number of rectangle areas to be blitted. The other (<b>wStateCount</b>-1) RECT structures required follow the D3DHAL_DP2CLEAR structure without any padding.


## -remarks



This structure is used with the D3DDP2OP_CLEAR command token to replace the legacy <b>D3dClear</b> and <b>D3dClear2</b> callbacks.

It is important to note that when the number of rectangles is zero, the D3DHAL_DP2CLEAR data structure still includes space for a single RECT. Thus, the size of this single RECT should be included when advancing to the next DP2 instruction. However, the contents of the RECT in this case are undefined and the driver should not attempt to read them.

Display drivers must convert input color values for the ARGB and YUV classes of color formats. For clear operations, input color values are specified in the <b>dwFillColor</b> member. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/handling-color-values-for-pixel-formats">Handling Color Values for Pixel Formats</a>.




## -see-also




D3DDP2OP_CLEAR



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ddpixelformat">DDPIXELFORMAT</a>
 

 

