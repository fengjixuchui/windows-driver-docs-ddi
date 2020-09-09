---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOPROCESSOR_0021
title: PFND3D12DDI_CREATEVIDEOPROCESSOR_0021 (d3d12umddi.h)
description: The pfnCreateVideoProcessor callback function creates a video processor.
old-location: display\pfnd3d12ddi_createvideoprocessor.htm
ms.assetid: 4F1AA75F-DDC7-490B-8CE2-590691991234
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_CREATEVIDEOPROCESSOR_0021 callback function"]
ms.keywords: PFND3D12DDI_CREATEVIDEOPROCESSOR_0021, PFND3D12DDI_CREATEVIDEOPROCESSOR_0021 callback, d3d12umddi/pfnCreateVideoProcessor, display.pfnd3d12ddi_createvideoprocessor, pfnCreateVideoProcessor, pfnCreateVideoProcessor callback function [Display Devices]
f1_keywords:
 - "d3d12umddi/pfnCreateVideoProcessor"
 - "pfnCreateVideoProcessor"
req.header: d3d12umddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d12umddi.h
api_name:
- pfnCreateVideoProcessor
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CREATEVIDEOPROCESSOR_0021 callback function


## -description


The <i>pfnCreateVideoProcessor</i> callback function creates a video processor.


## -parameters




### -param hDrvDevice

The handle of a device driver.


### -param pArgs


### -param hDrvVideoProcessor

The handle of a video processor.


## -returns



If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.



