---
UID: NC:d3d12umddi.PFND3D12DDI_RECLAIMRESOURCES_0001
title: PFND3D12DDI_RECLAIMRESOURCES_0001 (d3d12umddi.h)
description: Implemented by the client driver to reclaim resources.
ms.assetid: 3a8ee9d9-b122-4fe8-8243-70c3872ab95d
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
 - "d3d12umddi/PFND3D12DDI_RECLAIMRESOURCES_0001"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_RECLAIMRESOURCES_0001
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_RECLAIMRESOURCES_0001 callback function

## -description

Implemented by the client driver to reclaim resources.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_RECLAIMRESOURCES_0001 structure.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_RECLAIMRESOURCES_0001 Pfnd3d12ddiReclaimresources0001; 

// Definition

HRESULT Pfnd3d12ddiReclaimresources0001 
(
	 D3D12DDI_HDEVICE
	D3D12DDIARG_RECLAIMRESOURCES_0001 *
)
{...}

PFND3D12DDI_RECLAIMRESOURCES_0001 


```

## -remarks

## -see-also

