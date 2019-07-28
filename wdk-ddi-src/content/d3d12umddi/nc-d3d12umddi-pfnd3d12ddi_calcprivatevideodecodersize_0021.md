---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021
title: PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021 (d3d12umddi.h)
description: The pfnCalcPrivateVideoDecoderSize callback function calculates the size of a private video decoder.
old-location: display\pfnd3d12ddi_calcprivatevideodecodersize.htm
ms.assetid: 29A0CB0F-3469-4EF5-8C5B-132321F6C8E8
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021, PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021 callback, d3d12umddi/pfnCalcPrivateVideoDecoderSize, display.pfnd3d12ddi_calcprivatevideodecodersize, pfnCalcPrivateVideoDecoderSize, pfnCalcPrivateVideoDecoderSize callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d12umddi/pfnCalcPrivateVideoDecoderSize"
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
- pfnCalcPrivateVideoDecoderSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021 callback function


## -description


The <i>pfnCalcPrivateVideoDecoderSize</i> callback function calculates the size of a private video decoder.


## -parameters


### -param hDrvDevice

The hardware device being processed

### -param *pArgs

*CreateVideoDecoder* [in]

The arguments used to create a video decoder.



## -remarks



The runtime allocates memory for storing the driver CPU object that represents the video decoder.  This method is used to calculate the driver object size.



