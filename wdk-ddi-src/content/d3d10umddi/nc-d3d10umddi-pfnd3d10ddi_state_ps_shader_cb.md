---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_PS_SHADER_CB
title: PFND3D10DDI_STATE_PS_SHADER_CB (d3d10umddi.h)
description: The pfnStatePsShaderCb function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's shader program.
old-location: display\pfnstatepsshadercb.htm
ms.assetid: 0865e79e-7df9-4dc7-a655-4fbd0af72030
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_STATE_PS_SHADER_CB, PFND3D10DDI_STATE_PS_SHADER_CB callback, d3d10state_functions_f0180480-dc5e-4d36-8db7-4f32e9e09fc7.xml, d3d10umddi/pfnStatePsShaderCb, display.pfnstatepsshadercb, pfnStatePsShaderCb, pfnStatePsShaderCb callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnStatePsShaderCb"
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
- pfnStatePsShaderCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_PS_SHADER_CB callback function


## -description


The <b>pfnStatePsShaderCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's shader program.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

