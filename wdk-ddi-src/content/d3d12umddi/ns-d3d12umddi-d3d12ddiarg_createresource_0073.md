---
UID: NS:d3d12umddi.D3D12DDIARG_CREATERESOURCE_0073
title: D3D12DDIARG_CREATERESOURCE_0073
ms.date: 03/24/2020
ms.topic: language-reference
ms.assetid: 013da67b-2947-4481-a9c5-73d76e3244ac
tech.root: display
targetos: Windows
description: A structure containing information needed to describe the creation or size calculation of a resource.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATERESOURCE_0073
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATERESOURCE_0073
f1_keywords:
 - D3D12DDIARG_CREATERESOURCE_0073
 - d3d12umddi/D3D12DDIARG_CREATERESOURCE_0073
dev_langs:
 - c++
---

## -description

A structure containing information needed to describe the creation or size calculation of a resource.

## -struct-fields

### -field ReuseBufferGPUVA

The GPU-side virtual address this resource should have, if it does not need a new one assigned.

### -field ResourceType

The dimension of this resource. That is, whether it is a buffer, one-dimensional texture, two-dimensional texture, or so on.

### -field Width

The width of the resource. This is in texels, if the resource is a texture, or bytes if the resource is a buffer.

### -field Height

The height of the resource. This applies to two-dimensional and three-dimensional textures.

### -field DepthOrArraySize

The depth, or array size of the resource used when the resource is three-dimensional, or arrayed respectively.

### -field MipLevels

The number of mip levels the resource has.

### -field Format

Specifies how the resource's data is to be interpreted, using a [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) enumeration value.

### -field SampleDesc

Specifies the sample count and quality level of this resource, as it relates to multisampling.

### -field Layout

Specifies details related to how the memory which comprises the resource is arranged.

### -field Flags

Specifies bitwise-OR-ed flags which describe the ways the resource is to be used.

### -field InitialResourceState

Specifies the initial resource state.

### -field pRowMajorLayout

When **Layout** is D3D12DDI_TL_ROW_MAJOR and **pRowMajorLayout** is non-null, then ***pRowMajorLayout** specifies the layout of the resource.

### -field SamplerFeedbackDesc

Deprecated. Use [**D3D12DDIARG_CREATERESOURCE_0075**](ns-d3d12umddi-d3d12ddiarg_createresource_0075.md) for sampler feedback.

## -remarks

## -see-also

[**D3D12DDIARG_CREATERESOURCE_0075**](ns-d3d12umddi-d3d12ddiarg_createresource_0075.md)