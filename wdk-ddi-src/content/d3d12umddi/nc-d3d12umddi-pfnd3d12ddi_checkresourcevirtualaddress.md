---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS
title: PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS (d3d12umddi.h)
description: Check resource virtual address.
ms.assetid: e54aa0b0-c2ef-44db-9053-3ceeb71cf9a8
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS callback function"]
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
 - "d3d12umddi/PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS callback function

## -description

Check resource virtual address.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

## -returns

Returns D3D12DDI_GPU_VIRTUAL_ADDRESS.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS Pfnd3d12ddiCheckresourcevirtualaddress; 

// Definition

D3D12DDI_GPU_VIRTUAL_ADDRESS Pfnd3d12ddiCheckresourcevirtualaddress 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_CHECKRESOURCEVIRTUALADDRESS 


```

## -remarks

## -see-also

