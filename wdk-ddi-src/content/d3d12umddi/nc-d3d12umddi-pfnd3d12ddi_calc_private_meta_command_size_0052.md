---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052
title: PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 (d3d12umddi.h)
description: Calculates the private meta-command size.
ms.assetid: 072a7577-00ed-4c07-b0b3-112cad845491
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052"
 - "PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 callback function

## -description

Calculates the private meta-command size.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param CommandId

The command id.

### -param NodeMask

The node mask of the command list.

### -param pCreationParameters

The creation parameters.

### -param CreationParametersDataSizeInBytes

The size of the creation parameters.

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 Pfnd3d12ddiCalcPrivateMetaCommandSize0052; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateMetaCommandSize0052 
(
	D3D12DDI_HDEVICE Arg1
	GUID CommandId
	UINT NodeMask
	CONST void *pCreationParameters
	SIZE_T CreationParametersDataSizeInBytes
)
{...}

```

## -remarks

## -see-also

