---
UID: NS:d3d12umddi.D3D12DDI_RAYTRACING_INSTANCE_DESC_0054
title: D3D12DDI_RAYTRACING_INSTANCE_DESC_0054 (d3d12umddi.h)
description: Describes a ray tracing instance.
ms.assetid: 4bb4b9cf-e076-4b9b-b231-6b69023582c0
ms.date: 10/19/2018
keywords: ["D3D12DDI_RAYTRACING_INSTANCE_DESC_0054 structure"]
ms.keywords: D3D12DDI_RAYTRACING_INSTANCE_DESC_0054, D3D12DDI_RAYTRACING_INSTANCE_DESC_0054,
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
req.typenames: D3D12DDI_RAYTRACING_INSTANCE_DESC_0054
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RAYTRACING_INSTANCE_DESC_0054
 - d3d12umddi/D3D12DDI_RAYTRACING_INSTANCE_DESC_0054
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RAYTRACING_INSTANCE_DESC_0054
dev_langs:
 - c++
---

# D3D12DDI_RAYTRACING_INSTANCE_DESC_0054 structure


## -description

Describes a ray tracing instance. This data structure is used in GPU memory during acceleration structure build, and is useful if generating instance data on the CPU first then uploading to the GPU.

## -struct-fields

### -field Transform

A 3x4 transform matrix in row major layout representing the instance-to-world transformation.

### -field InstanceID

An arbitrary 24-bit value in shader types.

### -field InstanceMask

An 8-bit mask assigned to the instance, which can be used to include or reject groups of instances on a per-ray basis. If the value is zero, the instance will never be included. Set this value to a nonzero value.

### -field InstanceContributionToHitGroupIndex

Per-instance contribution to add into shader table indexing to select the hit group to use.

### -field Flags

Flags to apply to the instance.

### -field AccelerationStructure

 
Address of the bottom-level acceleration structure that is being instanced. The address must be aligned to 256 bytes.

The memory pointed to must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE.

## -remarks

## -see-also

