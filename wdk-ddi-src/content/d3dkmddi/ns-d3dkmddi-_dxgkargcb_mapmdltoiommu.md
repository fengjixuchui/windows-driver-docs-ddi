---
UID: NS:d3dkmddi._DXGKARGCB_MAPMDLTOIOMMU
title: _DXGKARGCB_MAPMDLTOIOMMU (d3dkmddi.h)
description: Arguments used by the DXGKCB_MAPMDLTOIOMMU callback function.
ms.assetid: 2dc0bd13-f7d3-44b4-a1da-ee05ff63d832
ms.date: 10/19/2018
keywords: ["DXGKARGCB_MAPMDLTOIOMMU structure"]
ms.keywords: _DXGKARGCB_MAPMDLTOIOMMU, DXGKARGCB_MAPMDLTOIOMMU, *INOUT_PDXGKARGCB_MAPMDLTOIOMMU
req.header: d3dkmddi.h
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
req.typenames: DXGKARGCB_MAPMDLTOIOMMU
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_MAPMDLTOIOMMU
 - d3dkmddi/_DXGKARGCB_MAPMDLTOIOMMU
 - DXGKARGCB_MAPMDLTOIOMMU
 - d3dkmddi/DXGKARGCB_MAPMDLTOIOMMU
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_MAPMDLTOIOMMU
product:
 - Windows
---

# _DXGKARGCB_MAPMDLTOIOMMU structure


## -description

Arguments used by the [DXGKCB_MAPMDLTOIOMMU](nc-d3dkmddi-dxgkcb_mapmdltoiommu.md) callback function.

## -struct-fields

### -field pMdl

An MDL which must be populated with valid pages. The MDL and the pages it points to must remain unchanged until the corresponding unmap call is made.

### -field hMemoryHandle

A Dxgkrnl tracking handle for the allocation. This value should be passed to the corresponding [DXGKCB_UNMAPMDLFROMIOMMU](nc-d3dkmddi-dxgkcb_unmapmdlfromiommu.md) function.

## -see-also

[DXGKCB_MAPMDLTOIOMMU](nc-d3dkmddi-dxgkcb_mapmdltoiommu.md)

