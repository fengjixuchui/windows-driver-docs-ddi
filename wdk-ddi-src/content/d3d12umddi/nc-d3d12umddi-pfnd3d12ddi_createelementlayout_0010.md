---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEELEMENTLAYOUT_0010
title: PFND3D12DDI_CREATEELEMENTLAYOUT_0010 (d3d12umddi.h)
description: Creates an element layout.
ms.assetid: 4d9e1109-4d2c-4234-b989-0bc270a5fb0c
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATEELEMENTLAYOUT_0010"
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
- PFND3D12DDI_CREATEELEMENTLAYOUT_0010
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATEELEMENTLAYOUT_0010 callback function

## -description

Creates an element layout.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEELEMENTLAYOUT_0010 Pfnd3d12ddiCreateelementlayout0010; 

// Definition

VOID Pfnd3d12ddiCreateelementlayout0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATEELEMENTLAYOUT_0010 *
	 D3D12DDI_HELEMENTLAYOUT
)
{...}

PFND3D12DDI_CREATEELEMENTLAYOUT_0010 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_CREATEELEMENTLAYOUT_0010 structure.

### -param D3D12DDI_HELEMENTLAYOUT: 

An element layout handle.

## -returns

Returns VOID.
