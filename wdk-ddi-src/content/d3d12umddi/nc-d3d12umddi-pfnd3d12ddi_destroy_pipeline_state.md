---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_PIPELINE_STATE
title: PFND3D12DDI_DESTROY_PIPELINE_STATE (d3d12umddi.h)
description: Destroys the pipeline state.
ms.assetid: 0cb38426-c17a-4d72-b47b-b8b1afcd5588
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_DESTROY_PIPELINE_STATE"
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
- PFND3D12DDI_DESTROY_PIPELINE_STATE
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_DESTROY_PIPELINE_STATE callback function

## -description

Destroys the pipeline state.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROY_PIPELINE_STATE Pfnd3d12ddiDestroyPipelineState; 

// Definition

VOID Pfnd3d12ddiDestroyPipelineState 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HPIPELINESTATE
)
{...}

PFND3D12DDI_DESTROY_PIPELINE_STATE 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HPIPELINESTATE: 

A pipeline state handle.

## -returns

Returns VOID.

## -remarks




## -see-also
