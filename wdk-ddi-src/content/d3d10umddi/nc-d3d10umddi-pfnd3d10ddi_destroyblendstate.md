---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYBLENDSTATE
title: PFND3D10DDI_DESTROYBLENDSTATE (d3d10umddi.h)
description: The DestroyBlendState function destroys the specified blend state object. The blend state object can be destoyed only if it is not currently bound to a display device.
old-location: display\destroyblendstate.htm
ms.assetid: 56fc1ecf-fd4c-4d36-941b-8fa6cca3b6b4
ms.date: 05/10/2018
ms.keywords: DestroyBlendState, DestroyBlendState callback function [Display Devices], PFND3D10DDI_DESTROYBLENDSTATE, PFND3D10DDI_DESTROYBLENDSTATE callback, UserModeDisplayDriverDx10_Functions_8af7f412-da7f-4326-a681-41bdfb4a97bb.xml, d3d10umddi/DestroyBlendState, display.destroyblendstate
ms.topic: callback
f1_keywords:
 - "d3d10umddi/DestroyBlendState"
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
- DestroyBlendState
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DESTROYBLENDSTATE callback function


## -description


The <b>DestroyBlendState</b> function destroys the specified blend state object. The blend state object can be destoyed only if it is not currently bound to a display device. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hBlendState* [in]

A handle to the driver's private data for the blend state object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region. 





## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DestroyBlendState</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

