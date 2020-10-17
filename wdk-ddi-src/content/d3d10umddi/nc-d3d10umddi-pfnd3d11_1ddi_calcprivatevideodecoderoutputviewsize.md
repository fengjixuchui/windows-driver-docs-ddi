---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE (d3d10umddi.h)
description: Returns the number of bytes that the driver requires to store private data for the video decoder view state.
old-location: display\calcprivatevideodecoderoutputviewsize.htm
ms.assetid: d8daa501-13cf-4fba-ab98-b1a2d0325ce1
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE callback function"]
ms.keywords: CalcPrivateVideoDecoderOutputViewSize, CalcPrivateVideoDecoderOutputViewSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE, PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE callback, d3d10umddi/CalcPrivateVideoDecoderOutputViewSize, display.calcprivatevideodecoderoutputviewsize
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE
 - d3d10umddi/PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CalcPrivateVideoDecoderOutputViewSize
product:
 - Windows
---

# PFND3D11_1DDI_CALCPRIVATEVIDEODECODEROUTPUTVIEWSIZE callback function


## -description

Returns the number of bytes that the driver requires to store private data for the video decoder view state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pView* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure that describes the video decoder view.

## -returns

The required number of bytes for the video decoder view state.

## -remarks

The runtime will validate the members of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure before it calls this function.

This function is not expected to fail.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a>