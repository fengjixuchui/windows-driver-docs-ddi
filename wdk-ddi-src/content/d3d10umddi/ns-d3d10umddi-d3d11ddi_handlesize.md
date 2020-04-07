---
UID: NS:d3d10umddi.D3D11DDI_HANDLESIZE
title: D3D11DDI_HANDLESIZE (d3d10umddi.h)
description: The D3D11DDI_HANDLESIZE structure describes a handle.
old-location: display\d3d11ddi_handlesize.htm
ms.assetid: 9b785bee-289f-4f91-8183-c1dc2fa1fa6d
ms.date: 05/10/2018
keywords: ["D3D11DDI_HANDLESIZE structure"]
ms.keywords: D3D11DDI_HANDLESIZE, D3D11DDI_HANDLESIZE structure [Display Devices], UMDisplayDriver_Dx11param_Structs_4eedfbd5-b87d-42bb-9ec9-2efc75ad3464.xml, d3d10umddi/D3D11DDI_HANDLESIZE, display.d3d11ddi_handlesize
f1_keywords:
 - "d3d10umddi/D3D11DDI_HANDLESIZE"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_HANDLESIZE is supported beginning with the Windows 7 operating system.
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
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D11DDI_HANDLESIZE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11DDI_HANDLESIZE
---

# D3D11DDI_HANDLESIZE structure


## -description


The D3D11DDI_HANDLESIZE structure describes a handle.


## -struct-fields




### -field HandleType

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_handletype">D3D11DDI_HANDLETYPE</a>-typed value that identifies the handle type. 


### -field DriverPrivateSize

[in] The size, in bytes, of the driver-private memory space that holds the handle data. 


## -remarks



The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes">CheckDeferredContextHandleSizes</a> function verifies the size of the driver-private memory space that holds the handle data of a deferred context handle and returns the size in the <b>DriverPrivateSize</b> member of the D3D11DDI_HANDLESIZE structure that the <i>pHandleSize</i> parameter points to. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes">CheckDeferredContextHandleSizes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_handletype">D3D11DDI_HANDLETYPE</a>
 

 

