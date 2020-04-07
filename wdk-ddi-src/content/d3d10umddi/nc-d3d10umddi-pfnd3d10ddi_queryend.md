---
UID: NC:d3d10umddi.PFND3D10DDI_QUERYEND
title: PFND3D10DDI_QUERYEND (d3d10umddi.h)
description: The QueryEnd function marks the end of a sequence of graphics commands for a query and transitions the query to the &#0034;issued&#0034; state.
old-location: display\queryend.htm
ms.assetid: 5a231d7e-7e47-40ad-99d1-82661dec41d0
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_QUERYEND callback function"]
ms.keywords: PFND3D10DDI_QUERYEND, PFND3D10DDI_QUERYEND callback, QueryEnd, QueryEnd callback function [Display Devices], UserModeDisplayDriverDx10_Functions_9897bbe4-a58c-430b-815a-eb4360ce8043.xml, d3d10umddi/QueryEnd, display.queryend
f1_keywords:
 - "d3d10umddi/QueryEnd"
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
- QueryEnd
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_QUERYEND callback function


## -description


The <i>QueryEnd</i> function marks the end of a sequence of graphics commands for a query and transitions the query to the "issued" state. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2


*hQuery* [in]

A handle to the query object to end.


## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



If the driver supports the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querybegin">QueryBegin</a> function for a query operation, and if the Microsoft Direct3D runtime calls <i>QueryEnd</i> without call <i>QueryBegin</i>, the call is equivalent to first calling <i>QueryBegin</i> and then calling <i>QueryEnd</i> immediately afterward. In addition, the runtime cannot call <i>QueryEnd</i> on a predicate that is currently bound to the pipeline through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setpredication">SetPredication</a> function.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>QueryEnd</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querybegin">QueryBegin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setpredication">SetPredication</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

