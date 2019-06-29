---
UID: NC:d3d10umddi.PFND3D10_1DDI_CREATEBLENDSTATE
title: PFND3D10_1DDI_CREATEBLENDSTATE (d3d10umddi.h)
description: The CreateBlendState(D3D10_1) function creates a blend state.
old-location: display\createblendstate_d3d10_1_.htm
ms.assetid: 1b258f28-c386-477c-92d1-cb5918080dcf
ms.date: 05/10/2018
ms.keywords: CreateBlendState_d3d10_1_, CreateBlendState_d3d10_1_ callback function [Display Devices], PFND3D10_1DDI_CREATEBLENDSTATE, PFND3D10_1DDI_CREATEBLENDSTATE callback, UserModeDisplayDriverDx10_Functions_46b88f91-736c-4b72-9220-05f347b829f2.xml, d3d10umddi/CreateBlendState_d3d10_1_, display.createblendstate_d3d10_1_
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateBlendState(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
- CreateBlendState_d3d10_1_
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10_1DDI_CREATEBLENDSTATE callback function


## -description


The <b>CreateBlendState(D3D10_1)</b> function creates a blend state.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

pBlendDesc [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_1_ddi_blend_desc">D3D10_1_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a blend state. 

### -param Arg2

*hBlendState* [in]

A handle to the driver's private data for the blend state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize">CalcPrivateBlendStateSize(D3D10_1)</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its blend state object. 

### -param Arg3

*hRTBlendState* [in]

A handle to the blend state that the driver should use anytime it calls back into the Direct3D runtime. 





## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyblendstate">DestroyBlendState</a> function to destroy the handle that the <i>hBlendState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of blend-state objects on a device at one time. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize">CalcPrivateBlendStateSize(D3D10_1)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_1ddi_devicefuncs">D3D10_1DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_1_ddi_blend_desc">D3D10_1_DDI_BLEND_DESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

