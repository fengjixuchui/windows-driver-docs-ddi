---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
title: _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE (d3dkmddi.h)
description: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE describes the multi-plane overlay plane attributes, allocation, and video present network source identification number.
old-location: display\dxgk_multiplane_overlay_plane_with_source.htm
ms.assetid: 358C060B-23A0-4F02-A5D3-07ADC3435849
ms.date: 05/10/2018
keywords: ["DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE, DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE, display.dxgk_multiplane_overlay_plane_with_source
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
f1_keywords:
 - _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
 - d3dkmddi/_DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
 - DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
 - d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE structure

> [!NOTE] This structure has been replaced by [DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2](ns-d3dkmddi-_dxgk_multiplane_overlay_plane_with_source2.md).


## -description

<b>DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE</b>

Describes the multi-plane overlay plane attributes, allocation, and video present network source identification number.

## -struct-fields

### -field hAllocation

A handle to the allocation.

### -field VidPnSourceId

The zero-based video present network source identification number of the input for which the support levels are queried.

### -field LayerIndex

The index of the layer being queried.

### -field PlaneAttributes

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes2">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</a> structure that specifies overlay plane attributes.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes2">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</a>

