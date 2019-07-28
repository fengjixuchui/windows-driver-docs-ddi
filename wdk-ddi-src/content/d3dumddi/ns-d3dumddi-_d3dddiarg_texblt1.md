---
UID: NS:d3dumddi._D3DDDIARG_TEXBLT1
title: _D3DDDIARG_TEXBLT1 (d3dumddi.h)
description: Describes parameters for a texture bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_texblt1.htm
tech.root: display
ms.assetid: e11fd9b5-c3ad-4f8f-890c-30ca5ce4a57f
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_TEXBLT1, D3DDDIARG_TEXBLT1 structure [Display Devices], _D3DDDIARG_TEXBLT1, d3dumddi/D3DDDIARG_TEXBLT1, display.d3dddiarg_texblt1
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDIARG_TEXBLT1"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dumddi.h
api_name:
- D3DDDIARG_TEXBLT1
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_TEXBLT1
---

# _D3DDDIARG_TEXBLT1 structure


## -description


Describes parameters for a texture bit-block transfer (bitblt) operation.


## -struct-fields




### -field hDstResource

A handle to the destination resource.


### -field hSrcResource

A handle to the source resource.


### -field CubeMapFace

The face of a cube map.


### -field DstPoint

A <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagpoint">POINT</a> structure that describes the destination point where the source texture is copied.


### -field SrcRect

A <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure that describes the source texture to copy to the destination point.


### -field CopyFlags

A value that specifies characteristics of a copy operation as a bitwise OR of the values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-d3dddi_copy_flags">D3DDDI_COPY_FLAGS</a> enumeration type.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-d3dddi_copy_flags">D3DDDI_COPY_FLAGS</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagpoint">POINT</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>
 

 

