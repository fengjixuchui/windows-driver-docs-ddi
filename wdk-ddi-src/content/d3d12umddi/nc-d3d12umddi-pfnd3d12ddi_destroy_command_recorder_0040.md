---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_COMMAND_RECORDER_0040
title: PFND3D12DDI_DESTROY_COMMAND_RECORDER_0040 (d3d12umddi.h)
description: Implemented by the client driver to clean up command recorder resources.
ms.assetid: 361f2b22-ea1e-4535-a0e7-302dab683485
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_DESTROY_COMMAND_RECORDER_0040 callback function"]
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
 - "d3d12umddi/PFND3D12DDI_DESTROY_COMMAND_RECORDER_0040"
 - "PFND3D12DDI_DESTROY_COMMAND_RECORDER_0040"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROY_COMMAND_RECORDER_0040
product:
 - Windows
---

# PFND3D12DDI_DESTROY_COMMAND_RECORDER_0040 callback function

## -description

Implemented by the client driver to clean up command recorder resources.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A handle to the command recorder.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROY_COMMAND_RECORDER_0040 Pfnd3d12ddiDestroyCommandRecorder0040;

// Definition

VOID Pfnd3d12ddiDestroyCommandRecorder0040
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HCOMMANDRECORDER_0040
)
{...}

PFND3D12DDI_DESTROY_COMMAND_RECORDER_0040


```

## -see-also

