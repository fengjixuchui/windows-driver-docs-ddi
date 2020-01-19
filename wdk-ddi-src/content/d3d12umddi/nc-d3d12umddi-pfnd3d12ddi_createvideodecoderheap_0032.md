---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODERHEAP_0032
title: PFND3D12DDI_CREATEVIDEODECODERHEAP_0032 (d3d12umddi.h)
description: Used to create a video decoder heap.
old-location: display\pfnd3d12ddi_createvideodecoderheap_0032.htm
ms.assetid: EC383086-CE8F-4387-8F92-BEC8215A97DA
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_CREATEVIDEODECODERHEAP_0032, PFND3D12DDI_CREATEVIDEODECODERHEAP_0032 callback, PFND3D12DDI_CREATEVIDEODECODERHEAP_0032 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEVIDEODECODERHEAP_0032, display.pfnd3d12ddi_createvideodecoderheap_0032
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATEVIDEODECODERHEAP_0032"
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
- d3d12umddi.h
api_name:
- PFND3D12DDI_CREATEVIDEODECODERHEAP_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CREATEVIDEODECODERHEAP_0032 callback function


## -description


Used to create a video decoder heap.


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param Arg2

pArgs [in]

The arguments used to create a video decoder heap.

### -param hDrvVideoDecoderHeap

The video decoder heap.




## -returns



Returns STATUS_SUCCESS if completed successfully.



