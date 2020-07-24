---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033
title: PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033 (d3d12umddi.h)
description: Used to calculate the size of a video decoder heap.
old-location: display\pfnd3d12ddi_calcprivatevideodecoderheapsize_0033.htm
ms.assetid: 4E635513-690F-4C23-8B2B-1B5FCAFE7F07
ms.date: 04/16/2018
keywords: ["PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033 callback function"]
ms.keywords: PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033, PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033 entry, PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033, display.pfnd3d12ddi_calcprivatevideodecoderheapsize_0033
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033"
 - "PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033
product:
 - Windows
---

# PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033 callback function

## -description

Used to calculate the size of a video decoder heap. The D3D runtime allocates memory for storing the drivers cpu object representing the video decoder heap.

## -parameters

### -param hDrvDevice

The hardware device being processed.

### -param pArgs

The arguments used to create a video decoder heap.

## -returns

Returns the size of the heap in bytes.

