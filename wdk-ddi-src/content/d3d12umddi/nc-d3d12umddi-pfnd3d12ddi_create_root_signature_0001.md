---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_ROOT_SIGNATURE_0001
title: PFND3D12DDI_CREATE_ROOT_SIGNATURE_0001 (d3d12umddi.h)
description: Create a root signature.
ms.assetid: d490391a-016e-480f-a9b7-db2182f62b52
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATE_ROOT_SIGNATURE_0001 callback function"]
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
 - "d3d12umddi/PFND3D12DDI_CREATE_ROOT_SIGNATURE_0001"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_ROOT_SIGNATURE_0001
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATE_ROOT_SIGNATURE_0001 callback function

## -description

Create a root signature.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_CREATE_ROOT_SIGNATURE_0001 structure.

### -param Arg3

A handle to a root signature.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_ROOT_SIGNATURE_0001 Pfnd3d12ddiCreateRootSignature0001; 

// Definition

HRESULT Pfnd3d12ddiCreateRootSignature0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_ROOT_SIGNATURE_0001 *
	 D3D12DDI_HROOTSIGNATURE
)
{...}

PFND3D12DDI_CREATE_ROOT_SIGNATURE_0001 


```

