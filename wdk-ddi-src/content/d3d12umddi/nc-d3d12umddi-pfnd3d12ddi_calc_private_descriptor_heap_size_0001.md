---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001
title: PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001 (d3d12umddi.h)
description: Calculates the size of the descriptor heap.
ms.assetid: 89ec24a0-5787-430b-9bc2-6adfbd6570a4
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001 callback function"]
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
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001 callback function

## -description

Calculates the size of the descriptor heap.

## -parameters

### -param Arg1

### -param Arg2

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001 Pfnd3d12ddiCalcPrivateDescriptorHeapSize0001; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateDescriptorHeapSize0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_DESCRIPTOR_HEAP_0001 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_DESCRIPTOR_HEAP_SIZE_0001 


```

## -remarks

## -see-also

