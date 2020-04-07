---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_VS_SHADER_CB
title: PFND3D10DDI_STATE_VS_SHADER_CB (d3d10umddi.h)
description: The pfnStateVsShaderCb function causes the Microsoft Direct3D 10 runtime to refresh the vertex shader stage's shader program.
old-location: display\pfnstatevsshadercb.htm
ms.assetid: f43f7dea-26a6-4e3f-99e2-5e3488a621b0
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_STATE_VS_SHADER_CB callback function"]
ms.keywords: PFND3D10DDI_STATE_VS_SHADER_CB, PFND3D10DDI_STATE_VS_SHADER_CB callback, d3d10state_functions_e9873351-ceaf-4cc2-9f92-7b3708d803bd.xml, d3d10umddi/pfnStateVsShaderCb, display.pfnstatevsshadercb, pfnStateVsShaderCb, pfnStateVsShaderCb callback function [Display Devices]
f1_keywords:
 - "d3d10umddi/pfnStateVsShaderCb"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- pfnStateVsShaderCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_VS_SHADER_CB callback function


## -description


The <b>pfnStateVsShaderCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the vertex shader stage's shader program.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

