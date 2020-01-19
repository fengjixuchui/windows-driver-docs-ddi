---
UID: NS:d3d12umddi.D3D12DDIARG_TEX1D_SHADER_RESOURCE_VIEW
title: D3D12DDIARG_TEX1D_SHADER_RESOURCE_VIEW (d3d12umddi.h)
description: Describes a one-dimensional (1-D) texture that is used to create a shader resource view.
ms.assetid: 94b6f165-eb7b-45e2-9cba-4ed0ad313d2d
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_TEX1D_SHADER_RESOURCE_VIEW"
ms.keywords: D3D12DDIARG_TEX1D_SHADER_RESOURCE_VIEW, D3D12DDIARG_TEX1D_SHADER_RESOURCE_VIEW, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDIARG_TEX1D_SHADER_RESOURCE_VIEW
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDIARG_TEX1D_SHADER_RESOURCE_VIEW
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# D3D12DDIARG_TEX1D_SHADER_RESOURCE_VIEW structure

## -description

Describes a one-dimensional (1-D) texture that is used to create a shader resource view.

## -struct-fields

### -field MostDetailedMip

The identifier of the most detailed MIP-map.

### -field FirstArraySlice

The identifier of the first array slice.

### -field MipLevels

The number of MIP-map levels for the texture.

### -field ArraySize

The number of array slices for the texture.

### -field ResourceMinLODClamp
 
A value to clamp sample LOD values to. For example, if you specify 2.0f for the clamp value, you ensure that no individual sample accesses a mip level less than 2.0f.

## -remarks

## -see-also
