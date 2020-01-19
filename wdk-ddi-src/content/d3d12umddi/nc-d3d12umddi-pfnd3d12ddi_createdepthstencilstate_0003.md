---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0003
title: PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0003 (d3d12umddi.h)
description: The PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0003 callback function creates a depth stencil state.
ms.assetid: 10f04c3d-f9bd-45fa-886d-662e9cd58fd4
ms.date: 10/19/2018
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0003"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0003
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0003 callback function

## -description

The PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0003 callback function creates a depth stencil state.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A pointer to a [D3D12DDI_DEPTH_STENCIL_DESC](ns-d3d12umddi-d3d12ddi_depth_stencil_desc.md) structure that describes the parameters that the user-mode display driver uses to create a depth stencil state.

### -param Arg3

A handle to the driver's private data for the depth stencil state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's [CalcPrivateDepthStencilStateSize](nc-d3d12umddi-pfnd3d12ddi_calcprivatedepthstencilstatesize.md) function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its depth stencil state object.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0003 Pfnd3d12ddiCreatedepthstencilstate0003; 

// Definition

VOID Pfnd3d12ddiCreatedepthstencilstate0003 
(
	D3D12DDI_HDEVICE hDevice
	CONST D3D12DDI_DEPTH_STENCIL_DESC *pDepthStencilDesc
	D3D12DDI_HDEPTHSTENCILSTATE hDepthStencilState
)
{...}

```

## -see-also

