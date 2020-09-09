---
UID: NS:d3dkmthk._D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2
title: _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2 (d3dkmthk.h)
description: Check multiplane overlay plane.
ms.assetid: 5c2a90f1-cab7-4789-8423-96c36867727a
ms.date: 10/19/2018
keywords: ["D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2 structure"]
ms.keywords: _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2, D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2
 - d3dkmthk/_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2
 - D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2
 - d3dkmthk/D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2
dev_langs:
 - c++
---

# _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE2 structure

> [!NOTE] This structure has been replaced by [D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3](ns-d3dkmthk-_d3dkmt_check_multiplane_overlay_plane3.md).


## -description

Check multiplane overlay plane.

## -struct-fields

### -field LayerIndex

The layer index.

### -field hResource

Handle for this resource in this process.

### -field CompSurfaceLuid

The component surface LUID (locally unique identifier).

### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field PlaneAttributes

 
Pointer to a D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES2 structure that contains the plane attributes.

## -remarks

## -see-also

