---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYRESOURCE
title: PFND3D10DDI_DESTROYRESOURCE (d3d10umddi.h)
description: The DestroyResource(D3D10) function destroys the specified resource object. The resource object can be destoyed only if it is not currently bound to a display device, and if all views that refer to the resource are also destroyed.
old-location: display\destroyresource_d3d10_.htm
ms.assetid: 3ff77844-eeee-4fda-8798-2e240bc51379
ms.date: 05/10/2018
ms.keywords: DestroyResource, DestroyResource callback function [Display Devices], PFND3D10DDI_DESTROYRESOURCE, PFND3D10DDI_DESTROYRESOURCE callback, UserModeDisplayDriverDx10_Functions_59a8abb1-fb74-49b0-a6b8-c0e867f9d7d6.xml, d3d10umddi/DestroyResource, display.destroyresource_d3d10_
ms.topic: callback
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
- DestroyResource
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DESTROYRESOURCE callback function


## -description


The <b>DestroyResource(D3D10)</b> function destroys the specified resource object. The resource object can be destoyed only if it is not currently bound to a display device, and if all views that refer to the resource are also destroyed. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hResource* [in]

A handle to the driver's private data for the resource object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region. 


## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DestroyResource(D3D10)</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

