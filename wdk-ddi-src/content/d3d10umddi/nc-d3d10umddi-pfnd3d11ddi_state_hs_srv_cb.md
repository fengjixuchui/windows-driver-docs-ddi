---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_HS_SRV_CB
title: PFND3D11DDI_STATE_HS_SRV_CB (d3d10umddi.h)
description: The pfnStateHsSrvCb function causes the Microsoft Direct3D 11 runtime to refresh the constant shader resource view state for the hull shader.
old-location: display\pfnstatehssrvcb.htm
ms.assetid: 93a0a6b2-6a1a-4cef-ad7e-c5b606d11c17
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_STATE_HS_SRV_CB callback function"]
ms.keywords: PFND3D11DDI_STATE_HS_SRV_CB, PFND3D11DDI_STATE_HS_SRV_CB callback, d3d10umddi/pfnStateHsSrvCb, d3d11state_functions_dfb556c1-522f-40b1-b5dd-ddfa4a4fc557.xml, display.pfnstatehssrvcb, pfnStateHsSrvCb, pfnStateHsSrvCb callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateHsSrvCb is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_STATE_HS_SRV_CB
 - d3d10umddi/PFND3D11DDI_STATE_HS_SRV_CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - pfnStateHsSrvCb
---

# PFND3D11DDI_STATE_HS_SRV_CB callback function


## -description

The <b>pfnStateHsSrvCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the constant shader resource view state for the hull shader.

## -parameters

### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function.

### -param Arg2

*Base* [in]

The beginning resource view for which the runtime should refresh state.

### -param Arg3

*Count* [in]

The total number of resource views. The number can be -1, which specifies that the Direct3D runtime uses its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>