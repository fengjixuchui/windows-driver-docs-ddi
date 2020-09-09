---
UID: NS:d3dhal._D3DHAL_DP2INDEXEDTRIANGLELIST2
title: _D3DHAL_DP2INDEXEDTRIANGLELIST2 (d3dhal.h)
description: One or more D3DHAL_DP2INDEXEDTRIANGLELIST2 structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLELIST2, and are used to render a sequence of unconnected triangles using vertex indices.
old-location: display\d3dhal_dp2indexedtrianglelist2.htm
tech.root: display
ms.assetid: 04d11aef-2766-42d6-abda-f0b25d53ef8f
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2INDEXEDTRIANGLELIST2 structure"]
ms.keywords: "*LPD3DHAL_DP2INDEXEDTRIANGLELIST2, D3DHAL_DP2INDEXEDTRIANGLELIST2, D3DHAL_DP2INDEXEDTRIANGLELIST2 structure [Display Devices], LPD3DHAL_DP2INDEXEDTRIANGLELIST2, LPD3DHAL_DP2INDEXEDTRIANGLELIST2 structure pointer [Display Devices], _D3DHAL_DP2INDEXEDTRIANGLELIST2, d3dhal/D3DHAL_DP2INDEXEDTRIANGLELIST2, d3dhal/LPD3DHAL_DP2INDEXEDTRIANGLELIST2, d3dstrct_7f47a0e0-7be5-46bf-89c3-fa69ee6e6230.xml, display.d3dhal_dp2indexedtrianglelist2"
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
req.typenames: D3DHAL_DP2INDEXEDTRIANGLELIST2, *LPD3DHAL_DP2INDEXEDTRIANGLELIST2
f1_keywords:
 - _D3DHAL_DP2INDEXEDTRIANGLELIST2
 - d3dhal/_D3DHAL_DP2INDEXEDTRIANGLELIST2
 - LPD3DHAL_DP2INDEXEDTRIANGLELIST2
 - d3dhal/LPD3DHAL_DP2INDEXEDTRIANGLELIST2
 - D3DHAL_DP2INDEXEDTRIANGLELIST2
 - d3dhal/D3DHAL_DP2INDEXEDTRIANGLELIST2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_DP2INDEXEDTRIANGLELIST2
---

# _D3DHAL_DP2INDEXEDTRIANGLELIST2 structure


## -description

One or more D3DHAL_DP2INDEXEDTRIANGLELIST2 structures are parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDTRIANGLELIST2, and are used to render a sequence of unconnected triangles using vertex indices.

## -struct-fields

### -field wV1

Specifies the index to the vertex buffer location containing coordinate data for the first vertex of the triangle.

### -field wV2

Specifies the index to the vertex buffer location containing coordinate data for the second vertex of the triangle.

### -field wV3

Specifies the index to the vertex buffer location containing coordinate data for the third vertex of the triangle.

## -remarks

The D3DHAL_DP2INDEXEDTRIANGLELIST2 structure specifies unconnected triangles to render with a vertex buffer. The vertex indexes are specified by <i>wV1</i>, <i>wV2</i>, and <i>wV3</i>. All edges are visible. The number of triangles to render (that is, the number of D3DHAL_DP2INDEXEDTRIANGLELIST2 structures to process) is specified by the <b>wPrimitiveCount</b> field of D3DHAL_DP2COMMAND. All indexes are relative to a vertex whose index is <i>wVStart</i> from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2startvertex">D3DHAL_DP2STARTVERTEX</a>. The sequence in the command stream is D3DHAL_DP2COMMAND followed by D3DHAL_DP2STARTVERTEX followed by <b>wPrimitiveCount</b>D3DHAL_DP2INDEXEDTRIANGLELIST2 structures.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback parses D3DHAL_DP2INDEXEDTRIANGLELIST2 structure(s) from the command buffer and renders the triangles using vertex indexes when D3DHAL_DP2COMMAND is D3DDP2OP_INDEXEDTRIANGLELIST2. A D3DHAL_DP2STARTVERTEX structure immediately follows the D3DHAL_DP2COMMAND in the command stream. This allows a base index to be specified for all the indexes that follow it. Thus triangles can be easily relocated and no flags are necessary to specify the triangle edges as is the case with D3DDP2OP_INDEXEDTRIANGLELIST.

## -see-also

D3DDP2OP_INDEXEDTRIANGLELIST



D3DDP2OP_INDEXEDTRIANGLELIST2



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2startvertex">D3DHAL_DP2STARTVERTEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>

