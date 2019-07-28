---
UID: NS:d3dumddi._D3DDDIARG_CLEAR
title: _D3DDDIARG_CLEAR (d3dumddi.h)
description: The D3DDDIARG_CLEAR structure describes the parameters of a hardware-assisted clearing operation.
old-location: display\d3dddiarg_clear.htm
tech.root: display
ms.assetid: f437f94c-075e-43e6-bf28-0e7c7bd78c5a
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_CLEAR, D3DDDIARG_CLEAR structure [Display Devices], UMDisplayDriver_param_Structs_64efff84-8fe3-40d4-b823-27e4a235fd86.xml, _D3DDDIARG_CLEAR, d3dumddi/D3DDDIARG_CLEAR, display.d3dddiarg_clear
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDIARG_CLEAR"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_CLEAR
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CLEAR
---

# _D3DDDIARG_CLEAR structure


## -description


The D3DDDIARG_CLEAR structure describes the parameters of a hardware-assisted clearing operation. 


## -struct-fields




### -field Flags

[in] A UINT value that specifies which buffers the driver should clear and how the clear operation should be performed. This member can be a bitwise OR of the following values. For more information, see the Remarks section in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Clear</a> reference page.

| **Value** | **Meaning** | 
|:--|:--|
| D3DCLEAR_TARGET (0x00000001l) | The driver should clear the context's render target to the color that is specified by the FillColor member. This value is defined in D3d8types.h. | 
| D3DCLEAR_STENCIL (0x00000004l) | The driver should clear the context's stencil buffer to the value that is specified by the FillStencil member. This value is defined in D3d8types.h. | 
| D3DCLEAR_ZBUFFER (0x00000002l) | The driver should clear the context's depth buffer to the depth that is specified by the FillDepth member. This value is defined in D3d8types.h. | 
| D3DCLEAR_COMPUTERECTS (0x00000008l) | If rectangles are specified for clearing, the driver should clip them against the current viewport. If no rectangles are specified, the driver should clear the entire viewport. This value is defined in D3dhal.h. | 


### -field FillColor

[in] The color value that the driver should clear the context's render target to.


### -field FillDepth

[in] The value that the driver should use to set the depth in the context's depth buffer. This member can be a value in the range from 0.0 through 1.0. 


### -field FillStencil

[in] The value that the driver should clear the context's stencil buffer to. This member can be an integer in the range from 0 through 2ⁿ-1, where <i>n</i> is the number of bits in the stencil buffer.


## -remarks



In a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Clear</a> function, a pointer to a D3DDDIARG_CLEAR structure is passed in the <i>pData</i> parameter. The Microsoft Direct3D runtime passes information to the <i>NumRect</i> and <i>pRect</i> parameters in a call to the user-mode display driver's <b>Clear</b> function to specify the rectangular areas of the buffer that the driver should clear.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Clear</a>
 

 

