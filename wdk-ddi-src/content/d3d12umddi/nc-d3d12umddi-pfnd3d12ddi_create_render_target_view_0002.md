---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002
title: PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002 (d3d12umddi.h)
description: Creates a render target view.
ms.assetid: 0070a035-8fba-4aaa-b70f-2641ad32e906
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002 callback function"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002
 - d3d12umddi/PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002 callback function


## -description

Creates a render target view.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATE_RENDER_TARGET_VIEW_0002 structure.

### -param DestDescriptor

The CPU descriptor handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002 Pfnd3d12ddiCreateRenderTargetView0002; 

// Definition

VOID Pfnd3d12ddiCreateRenderTargetView0002 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_RENDER_TARGET_VIEW_0002 *
	D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptor
)
{...}

PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002 


```

