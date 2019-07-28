---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_OM_BLENDSTATE_CB
title: PFND3D10DDI_STATE_OM_BLENDSTATE_CB (d3d10umddi.h)
description: The pfnStateOmBlendStateCb function causes the Microsoft Direct3D 10 runtime to refresh the output merger blend state.
old-location: display\pfnstateomblendstatecb.htm
ms.assetid: 3cec9d99-0d15-4c61-9de2-ab203a56441d
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_STATE_OM_BLENDSTATE_CB, PFND3D10DDI_STATE_OM_BLENDSTATE_CB callback, d3d10state_functions_18da32ca-c230-4119-a721-cbb8511a8b7c.xml, d3d10umddi/pfnStateOmBlendStateCb, display.pfnstateomblendstatecb, pfnStateOmBlendStateCb, pfnStateOmBlendStateCb callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnStateOmBlendStateCb"
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
- pfnStateOmBlendStateCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_OM_BLENDSTATE_CB callback function


## -description


The <b>pfnStateOmBlendStateCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the output merger blend state.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



The <b>pfnStateOmBlendStateCb</b> function calls the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setblendstate">SetBlendState</a> function with the current blend state.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setblendstate">SetBlendState</a>
 

 

