---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_ROOT_SIGNATURE_SIZE_0013
title: PFND3D12DDI_CALC_PRIVATE_ROOT_SIGNATURE_SIZE_0013 (d3d12umddi.h)
description: Calculates the driver's root signature size. 
tech.root: display
ms.assetid: 75572755-4ff2-4cba-bb1a-ba7cbec6bcd7
ms.date: 11/28/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_ROOT_SIGNATURE_SIZE_0013"
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
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
 - PFND3D12DDI_CALC_PRIVATE_ROOT_SIGNATURE_SIZE_0013
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_CALC_PRIVATE_ROOT_SIGNATURE_SIZE_0013 callback function

## -description

Calculates the driver's root signature size. 

## -prototype

```
//Declaration

PFND3D12DDI_CALC_PRIVATE_ROOT_SIGNATURE_SIZE_0013 Pfnd3d12ddiCalcPrivateRootSignatureSize0013; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateRootSignatureSize0013 
(
	D3D12DDI_HDEVICE Arg1
	 const D3D12DDIARG_CREATE_ROOT_SIGNATURE_0013 *
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param *

Pointer to a D3D12DDIARG_CREATE_ROOT_SIGNATURE_0013 structure.


## -returns

Returns SIZE_T.

## -remarks




## -see-also
