---
UID: NS:d3dumddi._D3DDDIARG_FLIPOVERLAY
title: _D3DDDIARG_FLIPOVERLAY (d3dumddi.h)
description: The D3DDDIARG_FLIPOVERLAY structure describes a new resource to display on a given overlay.
old-location: display\d3dddiarg_flipoverlay.htm
tech.root: display
ms.assetid: 36ea4547-e9a0-49c9-8b45-903a2de60923
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_FLIPOVERLAY, D3DDDIARG_FLIPOVERLAY structure [Display Devices], UMDisplayDriver_param_Structs_078e5dd1-bbd8-4067-85a7-2474d18b1d40.xml, _D3DDDIARG_FLIPOVERLAY, d3dumddi/D3DDDIARG_FLIPOVERLAY, display.d3dddiarg_flipoverlay
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDIARG_FLIPOVERLAY"
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
- D3DDDIARG_FLIPOVERLAY
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_FLIPOVERLAY
---

# _D3DDDIARG_FLIPOVERLAY structure


## -description


The D3DDDIARG_FLIPOVERLAY structure describes a new resource to display on a given overlay. 


## -struct-fields




### -field hOverlay

[in] A handle to the overlay hardware to be flipped. 


### -field hSource

[in] A handle to the new resource to be displayed. This resource might be the same as the resource that was previously displayed if deinterlacing interleaved data.


### -field SourceIndex

[in] The zero-based index of the subresource to be displayed.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_flipoverlayflags">D3DDDI_FLIPOVERLAYFLAGS</a> structure that indicates, in bit-field flags, how to flip the resource.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_flipoverlayflags">D3DDDI_FLIPOVERLAYFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_flipoverlay">FlipOverlay</a>
 

 

