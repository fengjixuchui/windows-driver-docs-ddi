---
UID: NC:d3d12umddi.PFND3D12DDI_EVICT2
title: PFND3D12DDI_EVICT2 (d3d12umddi.h)
description: PFND3D12DDI_EVICT2 instructs the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.
ms.assetid: 2ebce9ab-3827-4fa4-848f-58c9eb10f82a
ms.date: 10/19/2018
ms.topic: callback
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
 - "d3d12umddi/PFND3D12DDI_EVICT2"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_EVICT2
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_EVICT2 callback function

## -description

PFND3D12DDI_EVICT2 instructs the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.

## -parameters

### -param Arg1

A handle to the display device.

### -param Arg2

A pointer to a [D3D12DDIARG_EVICT](ns-d3d12umddi-d3d12ddiarg_evict.md) structure that describes the memory pages to evict.

## -returns

If this callback function succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -prototype

```cpp
//Declaration

PFND3D12DDI_EVICT2 Pfnd3d12ddiEvict2; 

// Definition

HRESULT Pfnd3d12ddiEvict2 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_EVICT *
)
{...}

PFND3D12DDI_EVICT2 


```

## -remarks

Once the eviction request is queued, it is illegal to access the underlying allocation as the allocation may be evicted at anytime from there on at the operating system discretion.

## -see-also

