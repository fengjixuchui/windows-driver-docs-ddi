---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT
title: PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT (d3d12umddi.h)
description: Calculates the geometry shader with stream output.
tech.root: display
ms.assetid: 8a3e0549-12b2-449b-bf03-24946246877a
ms.date: 11/28/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT"
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3d12umddi.h
api_name: 
 - PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT callback function

## -description

Calculates the geometry shader with stream output.

## -prototype

```
//Declaration

PFND3D12DDI_CALC_PRIVATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT Pfnd3d12ddiCalcPrivateGeometryShaderWithStreamOutput; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateGeometryShaderWithStreamOutput 
(
	D3D12DDI_HDEVICE Arg1
	 const D3D12DDIARG_CREATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT *
	 const D3D12DDIARG_STAGE_IO_SIGNATURES *
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param *

Pointer to a D3D12DDIARG_CREATE_GEOMETRY_SHADER_WITH_STREAM_OUTPUT structure.

### -param *

Pointer to a D3D12DDIARG_STAGE_IO_SIGNATURES structure.

## -returns

Returns SIZE_T.

## -remarks




## -see-also
