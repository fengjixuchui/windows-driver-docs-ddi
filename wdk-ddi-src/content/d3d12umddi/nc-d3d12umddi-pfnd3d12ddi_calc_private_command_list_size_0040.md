---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0040
title: PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0040 (d3d12umddi.h)
description: The CalcPrivateCommandListSize function determines the size of the user-mode display driver's private region of memory for a command list.
ms.assetid: e49f46eb-58ad-4bf8-820a-2e33cfd099fb
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
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0040"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0040
product:
 - Windows
---

# PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0040 callback function

## -description

The CalcPrivateCommandListSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a command list.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATE_COMMAND_LIST_0040 structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

Returns the size of the memory region that the driver requires to create a command list.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0040 Pfnd3d12ddiCalcPrivateCommandListSize0040;

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateCommandListSize0040
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_COMMAND_LIST_0040 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_COMMAND_LIST_SIZE_0040


```

## -remarks

The driver is only required to implement CalcPrivateCommandListSize if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the D3D11DDI_THREADING_CAPS structure from a call to the GetCaps(D3D10_2) function.

## -see-also

