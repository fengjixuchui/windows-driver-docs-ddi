---
UID: NC:d3d12umddi.PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062
title: PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062
description: When an application changes background processing mode, PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062 is called to inform the UMD of the new settings.
tech.root: display
ms.assetid: 5165a123-6ae6-41bb-9ce7-c152dfc0bb89
ms.date: 04/04/2019
keywords: ["PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
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
ms.custom: D3D12 Release 6, Build rev 2., 19H1
f1_keywords:
 - PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062
 - d3d12umddi/PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062
dev_langs:
 - c++
---

# PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062 callback function


## -description

When an application changes background processing mode, PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062 is called to inform the UMD of the new settings.

## -parameters

### -param hRTDevice

[in] The handle of the device for the driver to use when it calls back into the runtime.

### -param Mode

A [D3D12DDI_BACKGROUND_PROCESSING_MODE_0062](ne-d3d12umddi-d3d12ddi_background_processing_mode_0062.md) enumeration that represents the background processing mode.

### -param MeasurementsAction

A [D3D12DDI_MEASUREMENTS_ACTION_0062](ne-d3d12umddi-d3d12ddi_measurements_action_0062.md) enumeration that represents the measurement action.

## -prototype

```
//Declaration

PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0062 Pfnd3d12ddiSetBackgroundProcessingMode0062; 

// Definition

void Pfnd3d12ddiSetBackgroundProcessingMode0062 
(
	D3D12DDI_HDEVICE hRTDevice
	D3D12DDI_BACKGROUND_PROCESSING_MODE_0062 Mode
	D3D12DDI_MEASUREMENTS_ACTION_0062 MeasurementsAction
)
{...}

```

## -remarks

Background processing work must only ever be used for optimization purposes. These work items must not affect functional correctness of the implementation.

## -see-also

