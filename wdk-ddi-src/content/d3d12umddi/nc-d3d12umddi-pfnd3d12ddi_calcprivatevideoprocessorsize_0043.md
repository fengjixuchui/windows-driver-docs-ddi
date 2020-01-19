---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043
title: PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043 (d3d12umddi.h)
description: Used to calculate the size of a video processor.
ms.assetid: d3793818-114a-4668-af13-b2eedbb39577
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
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043
product:
 - Windows
---

# PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043 callback function

## -description

This method is used to calculate the driver object size. The Direct3D runtime allocates memory for storing the drivers CPU object that represents the video processor.

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context).

### -param pArgs

The arguments used to create a video processor.

## -returns

Returns the size of the video processor in bytes.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043 Pfnd3d12ddiCalcprivatevideoprocessorsize0043;

// Definition

SIZE_T Pfnd3d12ddiCalcprivatevideoprocessorsize0043
(
	D3D12DDI_HDEVICE hDrvDevice
	CONST D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0043 *pArgs
)
{...}

PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043


```

## -remarks

## -see-also

