---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_HS_SHADER_CB
title: PFND3D11DDI_STATE_HS_SHADER_CB (d3d10umddi.h)
description: The pfnStateHsShaderCb function causes the Microsoft Direct3D 11 runtime to refresh the hull shader.
old-location: display\pfnstatehsshadercb.htm
ms.assetid: 74b243a2-722b-4eec-b382-936a6f2f990e
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_STATE_HS_SHADER_CB callback function"]
ms.keywords: PFND3D11DDI_STATE_HS_SHADER_CB, PFND3D11DDI_STATE_HS_SHADER_CB callback, d3d10umddi/pfnStateHsShaderCb, d3d11state_functions_b16162bf-d379-49de-bc4a-85d7df7e95bf.xml, display.pfnstatehsshadercb, pfnStateHsShaderCb, pfnStateHsShaderCb callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateHsShaderCb is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
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
 - PFND3D11DDI_STATE_HS_SHADER_CB
 - d3d10umddi/PFND3D11DDI_STATE_HS_SHADER_CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - pfnStateHsShaderCb
---

# PFND3D11DDI_STATE_HS_SHADER_CB callback function


## -description

The <b>pfnStateHsShaderCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the hull shader.

## -parameters

### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>

