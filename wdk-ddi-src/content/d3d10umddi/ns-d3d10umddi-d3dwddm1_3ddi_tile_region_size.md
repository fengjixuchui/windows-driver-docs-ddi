---
UID: NS:d3d10umddi.D3DWDDM1_3DDI_TILE_REGION_SIZE
title: D3DWDDM1_3DDI_TILE_REGION_SIZE (d3d10umddi.h)
description: Specifies a tiled region.
old-location: display\d3dwddm1_3ddi_tile_region_size.htm
ms.assetid: 276ED4AC-15D9-4550-AC51-83320DE9D5B2
ms.date: 05/10/2018
keywords: ["D3DWDDM1_3DDI_TILE_REGION_SIZE structure"]
ms.keywords: D3DWDDM1_3DDI_TILE_REGION_SIZE, D3DWDDM1_3DDI_TILE_REGION_SIZE structure [Display Devices], d3d10umddi/D3DWDDM1_3DDI_TILE_REGION_SIZE, display.d3dwddm1_3ddi_tile_region_size
f1_keywords:
 - "d3d10umddi/D3DWDDM1_3DDI_TILE_REGION_SIZE"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
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
- D3d10umddi.h
api_name:
- D3DWDDM1_3DDI_TILE_REGION_SIZE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM1_3DDI_TILE_REGION_SIZE
---

# D3DWDDM1_3DDI_TILE_REGION_SIZE structure


## -description


Specifies a tiled region.


## -struct-fields




### -field NumTiles

The number of tiles within the tiled region.

<div class="alert"><b>Note</b>  <b>NumTiles</b> must equal <b>Width</b> * <b>Height</b> * <b>Depth</b>.</div>
<div> </div>

### -field bUseBox

If <b>TRUE</b>, the tiled region is defined by the <b>Width</b>, <b>Height</b>, and <b>Depth</b> members. In this case, one update region cannot span mipmaps, although it can span array slices using the  <b>Depth</b> member.

If <b>FALSE</b>, the <b>Width</b>, <b>Height</b>, and <b>Depth</b> members should be ignored, and the tiled region is defined by the <b>NumTiles</b> member. In this case, tiles are mapped linearly, first across the <i>x</i>-direction, then the <i>y</i>-direction, then (as applicable) across the <i>z</i>-direction, and then spilling over mipmaps and arrays in subresource order. This procedure is useful for mapping an entire resource at one time.

In either case, the starting location for the region within the resource 
                  is specified as a separate parameter outside this structure.


### -field Width

The width (in the <i>x</i>-direction) of the tiled region. Used for buffer, 1-D, 2-D, and 3-D rendering.


### -field Height

The height (in the <i>y</i>-direction) of the tiled region. Used for 2-D and 3-D rendering.


### -field Depth

The depth (in the <i>z</i>-direction) of the tiled region. Used for 3-D rendering or for arrays. In the case of arrays, advancing in depth skips to the next slice of the same mipmap size.

