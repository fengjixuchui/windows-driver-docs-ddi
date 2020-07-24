---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYSHADER
title: PFND3D12DDI_DESTROYSHADER (d3d12umddi.h)
description: Destroy shader.
ms.assetid: 11ca0734-50b5-45a3-af8a-d344c88a2b68
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_DESTROYSHADER callback function"]
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
 - "d3d12umddi/PFND3D12DDI_DESTROYSHADER"
 - "PFND3D12DDI_DESTROYSHADER"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROYSHADER
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_DESTROYSHADER callback function

## -description

Destroy shader.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A shader handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYSHADER Pfnd3d12ddiDestroyshader; 

// Definition

VOID Pfnd3d12ddiDestroyshader 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HSHADER
)
{...}

PFND3D12DDI_DESTROYSHADER 


```

## -remarks

## -see-also

