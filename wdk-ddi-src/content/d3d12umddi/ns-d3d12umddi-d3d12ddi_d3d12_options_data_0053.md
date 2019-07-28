---
UID: NS:d3d12umddi.D3D12DDI_D3D12_OPTIONS_DATA_0053
title: D3D12DDI_D3D12_OPTIONS_DATA_0053 (d3d12umddi.h)
description: 
ms.assetid: 2d2e4d47-5b59-4da1-af25-7a1859ec42e9
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_D3D12_OPTIONS_DATA_0053"
ms.keywords: D3D12DDI_D3D12_OPTIONS_DATA_0053, D3D12DDI_D3D12_OPTIONS_DATA_0053, 
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
req.typenames: D3D12DDI_D3D12_OPTIONS_DATA_0053
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_D3D12_OPTIONS_DATA_0053
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_D3D12_OPTIONS_DATA_0053 structure

## -description


## -struct-fields

### -field ResourceBindingTier

Resource binding tier.


### -field ConservativeRasterizationTier

Conservative rasterization tier.


### -field TiledResourcesTier

Tiled resource tier.


### -field CrossNodeSharingTier

Cross node sharing tier.


### -field VPAndRTArrayIndexFromAnyShaderFeedingRasterizerSupportedWithoutGSEmulation

VP and RT array index from any shader feeding rasterizer supported without GS emulation.


### -field OutputMergerLogicOp

Output merger logic option.


### -field ResourceHeapTier

Resource heap tier.


### -field DepthBoundsTestSupported

Depth bounds test supported.


### -field ProgrammableSamplePositionsTier

Programmable sample positions tier.


### -field CopyQueueTimestampQueriesSupported

Copy queue timestamp queries supported.


### -field WriteBufferImmediateQueueFlags

Write buffer immediate queue flags.


### -field ViewInstancingTier

View instancing tier.


### -field BarycentricsSupported

Barycentrics supported.

### -field ReservedBufferPlacementSupported

Reserved buffer placement supported. Supports only just 64KB aligned MSAA.

### -field Deterministic64KBUndefinedSwizzle

Deterministic 64KB undefined swizzle.
 
### -field SRVOnlyTiledResourceTier3

Indicates whether the hardware supports SRV-only sparse volume textures.
 
### -field RenderPassTier

The [D3D12DDI_RENDER_PASS_TIER](ne-d3d12umddi-d3d12ddi_render_pass_tier.md) that the hardware supports. 


## -remarks

## -see-also
