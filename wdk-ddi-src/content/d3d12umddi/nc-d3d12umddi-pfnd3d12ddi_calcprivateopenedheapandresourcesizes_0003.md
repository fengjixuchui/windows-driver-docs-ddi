---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003
title: PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003 (d3d12umddi.h)
description: Calculates sizes for private opened heap and resources.
ms.assetid: fadc2a19-60d0-4c03-8f03-62bd629186ac
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003"
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
- PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003 callback function

## -description

Calculates sizes for private opened heap and resources.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003 Pfnd3d12ddiCalcprivateopenedheapandresourcesizes0003; 

// Definition

D3D12DDI_HEAP_AND_RESOURCE_SIZES Pfnd3d12ddiCalcprivateopenedheapandresourcesizes0003 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OPENHEAP_0003 *
)
{...}

PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_OPENHEAP_0003.

## -returns

Returns D3D12DDI_HEAP_AND_RESOURCE_SIZES.
