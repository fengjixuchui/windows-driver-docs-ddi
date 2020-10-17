---
UID: NS:d3dhal._D3DHAL_DP2SETRENDERTARGET
title: _D3DHAL_DP2SETRENDERTARGET (d3dhal.h)
description: The D3DHAL_DP2SETRENDERTARGET structure is used with the D3DDP2OP_SETRENDERTARGET opcode to map a new rendering target surface and depth buffer in the current context.
old-location: display\d3dhal_dp2setrendertarget.htm
tech.root: display
ms.assetid: 0ececf46-23a4-456b-8305-b9cd0ffba4b6
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2SETRENDERTARGET structure"]
ms.keywords: "*LPD3DHAL_DP2SETRENDERTARGET, D3DHAL_DP2SETRENDERTARGET, D3DHAL_DP2SETRENDERTARGET structure [Display Devices], LPD3DHAL_DP2SETRENDERTARGET, LPD3DHAL_DP2SETRENDERTARGET structure pointer [Display Devices], _D3DHAL_DP2SETRENDERTARGET, d3dhal/D3DHAL_DP2SETRENDERTARGET, d3dhal/LPD3DHAL_DP2SETRENDERTARGET, d3dstrct_d3f81bd9-d8fd-4560-b8b3-61af41d4a13b.xml, display.d3dhal_dp2setrendertarget"
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
req.typenames: D3DHAL_DP2SETRENDERTARGET
f1_keywords:
 - _D3DHAL_DP2SETRENDERTARGET
 - d3dhal/_D3DHAL_DP2SETRENDERTARGET
 - D3DHAL_DP2SETRENDERTARGET
 - d3dhal/D3DHAL_DP2SETRENDERTARGET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_DP2SETRENDERTARGET
---

# _D3DHAL_DP2SETRENDERTARGET structure


## -description

The D3DHAL_DP2SETRENDERTARGET structure is used with the D3DDP2OP_SETRENDERTARGET opcode to map a new rendering target surface and depth buffer in the current context.

## -struct-fields

### -field hRenderTarget

Specifies a handle to the rendering target.

### -field hZBuffer

Specifies a handle to the depth buffer.

## -remarks

The driver should carry out the following tasks in response to a D3DDP2OP_SETRENDERTARGET opcode in the <a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> command stream:

<ol>
<li>
Store the rendering target identified by <b>hRenderTarget</b> in the driver's context. 

</li>
<li>
Store the depth buffer identified by <b>hZBuffer</b> in the driver's context. 

</li>
</ol>
See the <i>p3samp</i> sample driver that ships with the Microsoft Windows Driver Development Kit (DDK) for more implementation details.

## -see-also

D3DDP2OP_SETRENDERTARGET



<a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>