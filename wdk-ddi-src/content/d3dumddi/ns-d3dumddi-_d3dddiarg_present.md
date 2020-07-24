---
UID: NS:d3dumddi._D3DDDIARG_PRESENT
title: _D3DDDIARG_PRESENT (d3dumddi.h)
description: The D3DDDIARG_PRESENT structure describes a resource to display.
old-location: display\d3dddiarg_present.htm
tech.root: display
ms.assetid: ee872d01-4bc6-46ce-80b7-3f73dd1a89ab
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_PRESENT structure"]
ms.keywords: D3DDDIARG_PRESENT, D3DDDIARG_PRESENT structure [Display Devices], UMDisplayDriver_param_Structs_1406aa28-1355-4e46-886f-9121fcbd7750.xml, _D3DDDIARG_PRESENT, d3dumddi/D3DDDIARG_PRESENT, display.d3dddiarg_present
f1_keywords:
 - "d3dumddi/D3DDDIARG_PRESENT"
 - "D3DDDIARG_PRESENT"
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
- D3DDDIARG_PRESENT
targetos: Windows
req.typenames: D3DDDIARG_PRESENT
---

# _D3DDDIARG_PRESENT structure


## -description


The D3DDDIARG_PRESENT structure describes a resource to display.


## -struct-fields




### -field hSrcResource

[in] A handle to the source resource to display. <b>hSrcResource</b> can be <b>NULL</b> if the user-mode display driver should perform a color-fill operation to the screen.


### -field SrcSubResourceIndex

[in] The zero-based index into the source resource, which is specified by the handle in the <b>hSrcResource</b> member. This index indicates the subresource or surface to display.


### -field hDstResource

[in] A handle to the destination resource to display to. If <b>NULL</b>, the user-mode display driver is informed that a color-fill operation will occur, but the user-mode driver is not expected to perform the operation. The display miniport driver does the actual color-fill operation and will be informed of the color value at that time.


### -field DstSubResourceIndex


      [in] The zero-based index into the destination resource, which is specified by the handle in the <b>hDstResource</b> member. This index indicates the subresource or surface to display to.
     


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_presentflags">D3DDDI_PRESENTFLAGS</a> structure that identifies, in bit-field flags, how to display. 


### -field FlipInterval

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_present">Present</a>
 

 

