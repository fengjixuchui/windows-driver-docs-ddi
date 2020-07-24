---
UID: NS:d3dumddi.D3DDDIARG_PRESENTSURFACE
title: D3DDDIARG_PRESENTSURFACE (d3dumddi.h)
description: Describes a surface to display.
old-location: display\d3dddiarg_presentsurface.htm
tech.root: display
ms.assetid: 2104BF68-DF35-44DE-AD83-3026FF9314B4
ms.date: 05/10/2018
keywords: ["D3DDDIARG_PRESENTSURFACE structure"]
ms.keywords: D3DDDIARG_PRESENTSURFACE, D3DDDIARG_PRESENTSURFACE structure [Display Devices], d3dumddi/D3DDDIARG_PRESENTSURFACE, display.d3dddiarg_presentsurface
f1_keywords:
 - "d3dumddi/D3DDDIARG_PRESENTSURFACE"
 - "D3DDDIARG_PRESENTSURFACE"
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
- D3DDDIARG_PRESENTSURFACE
targetos: Windows
req.typenames: D3DDDIARG_PRESENTSURFACE
---

# D3DDDIARG_PRESENTSURFACE structure


## -description


Describes a surface to display.


## -struct-fields




### -field hResource

[in] A handle to the resource that contains the surface. <b>hResource</b> can be <b>NULL</b> if the user-mode display driver should perform a color-fill operation to the screen.


### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource or surface to display.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_present">Present</a>
 

 

