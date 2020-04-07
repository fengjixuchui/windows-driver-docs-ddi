---
UID: NE:d3d12umddi.D3D12DDI_HEAP_FLAGS
title: D3D12DDI_HEAP_FLAGS (d3d12umddi.h)
description: Contains Direct3D 12 heap flags.
old-location: display\d3d12ddi_heap_flags.htm
ms.assetid: 8224E497-7F52-469B-98C9-ECC5F1970894
ms.date: 04/16/2018
keywords: ["D3D12DDI_HEAP_FLAGS enumeration"]
ms.keywords: D3D12DDI_HEAP_FLAGS, D3D12DDI_HEAP_FLAGS enumeration [Display Devices], D3D12DDI_HEAP_FLAG_BUFFERS, D3D12DDI_HEAP_FLAG_COHERENT_SYSTEMWIDE, D3D12DDI_HEAP_FLAG_CONTENT_PROTECTION, D3D12DDI_HEAP_FLAG_NONE, D3D12DDI_HEAP_FLAG_NON_RT_DS_TEXTURES, D3D12DDI_HEAP_FLAG_PRIMARY, D3D12DDI_HEAP_FLAG_RT_DS_TEXTURES, d3d12umddi/D3D12DDI_HEAP_FLAGS, d3d12umddi/D3D12DDI_HEAP_FLAG_BUFFERS, d3d12umddi/D3D12DDI_HEAP_FLAG_COHERENT_SYSTEMWIDE, d3d12umddi/D3D12DDI_HEAP_FLAG_CONTENT_PROTECTION, d3d12umddi/D3D12DDI_HEAP_FLAG_NONE, d3d12umddi/D3D12DDI_HEAP_FLAG_NON_RT_DS_TEXTURES, d3d12umddi/D3D12DDI_HEAP_FLAG_PRIMARY, d3d12umddi/D3D12DDI_HEAP_FLAG_RT_DS_TEXTURES, display.d3d12ddi_heap_flags
f1_keywords:
 - "d3d12umddi/D3D12DDI_HEAP_FLAGS"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_HEAP_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_HEAP_FLAGS
---

# D3D12DDI_HEAP_FLAGS enumeration


## -description


Contains Direct3D 12 heap flags.


## -enum-fields




### -field D3D12DDI_HEAP_FLAG_NONE

No flags.


### -field D3D12DDI_HEAP_FLAG_NON_RT_DS_TEXTURES

The heap supports resources allocated for other than Render Target (RT) and Depth-Stencil (DS) textures.


### -field D3D12DDI_HEAP_FLAG_BUFFERS

The heap supports resources allocated for buffers.


### -field D3D12DDI_HEAP_FLAG_COHERENT_SYSTEMWIDE

The heap supports resources allocated for coherent system wide.


### -field D3D12DDI_HEAP_FLAG_PRIMARY

The heap supports resources allocated for primary.


### -field D3D12DDI_HEAP_FLAG_RT_DS_TEXTURES

The heap supports resources allocated for RT and DS textures.

### -field D3D12DDI_HEAP_FLAG_0041_DENY_L0_DEMOTION

Supports transparent demotion to system memory by restricting the supported memory segments for the heap.

