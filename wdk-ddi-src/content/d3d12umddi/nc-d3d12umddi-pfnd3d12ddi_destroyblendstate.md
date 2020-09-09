---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYBLENDSTATE
title: PFND3D12DDI_DESTROYBLENDSTATE (d3d12umddi.h)
description: Destroys a blend state.
ms.assetid: eb4b3ebd-be63-41cf-af25-9c58ffe69deb
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_DESTROYBLENDSTATE callback function"]
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
 - PFND3D12DDI_DESTROYBLENDSTATE
 - d3d12umddi/PFND3D12DDI_DESTROYBLENDSTATE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROYBLENDSTATE
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_DESTROYBLENDSTATE callback function


## -description

Destroys a blend state.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A blend state handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYBLENDSTATE Pfnd3d12ddiDestroyblendstate; 

// Definition

VOID Pfnd3d12ddiDestroyblendstate 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HBLENDSTATE
)
{...}

PFND3D12DDI_DESTROYBLENDSTATE 


```

## -remarks

## -see-also

