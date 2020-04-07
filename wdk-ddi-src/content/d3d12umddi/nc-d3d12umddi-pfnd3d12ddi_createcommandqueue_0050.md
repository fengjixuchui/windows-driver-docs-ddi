---
UID: NC:d3d12umddi.PFND3D12DDI_CREATECOMMANDQUEUE_0050
title: PFND3D12DDI_CREATECOMMANDQUEUE_0050 (d3d12umddi.h)
description: The PFND3D12DDI_CREATECOMMANDQUEUE_0050 callback function is used to create command queue.
ms.assetid: 8119dd7e-eb0f-4636-beff-93773b28dfe8
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATECOMMANDQUEUE_0050 callback function"]
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
 - "d3d12umddi/PFND3D12DDI_CREATECOMMANDQUEUE_0050"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATECOMMANDQUEUE_0050
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATECOMMANDQUEUE_0050 callback function

## -description

The PFND3D12DDI_CREATECOMMANDQUEUE_0050 callback function is used to create command queue.

## -parameters

### -param Arg1

The handle of a device.

### -param Arg2

Pointer to a [D3D12DDIARG_CREATECOMMANDQUEUE_0050](ns-d3d12umddi-d3d12ddiarg_createcommandqueue_0050.md) structure that contains arguments used to create a command queue.

### -param Arg3

The handle of the command queue for the driver to use when it calls back into the runtime.

### -param Arg4

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATECOMMANDQUEUE_0050 Pfnd3d12ddiCreatecommandqueue0050; 

// Definition

HRESULT Pfnd3d12ddiCreatecommandqueue0050 
(
	D3D12DDI_HDEVICE Arg1
	CONST D3D12DDIARG_CREATECOMMANDQUEUE_0050 *
	D3D12DDI_HCOMMANDQUEUE Arg2
	D3D12DDI_HRTCOMMANDQUEUE Arg3
)
{...}

```

## -remarks

Access this callback function by using a device functions core structure, such as the [D3D12DDI_DEVICE_FUNCS_CORE_0050](ns-d3d12umddi-d3d12ddi_device_funcs_core_0050.md) structure.

## -see-also

