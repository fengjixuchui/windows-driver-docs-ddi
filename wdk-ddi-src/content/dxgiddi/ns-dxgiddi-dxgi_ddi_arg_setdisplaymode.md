---
UID: NS:dxgiddi.DXGI_DDI_ARG_SETDISPLAYMODE
title: DXGI_DDI_ARG_SETDISPLAYMODE (dxgiddi.h)
description: The DXGI_DDI_ARG_SETDISPLAYMODE structure describes parameters for setting the display mode.
old-location: display\dxgi_ddi_arg_setdisplaymode.htm
tech.root: display
ms.assetid: eb2b7470-cd23-4e0c-a887-42c47b881607
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_SETDISPLAYMODE structure"]
ms.keywords: DXGI_DDI_ARG_SETDISPLAYMODE, DXGI_DDI_ARG_SETDISPLAYMODE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_b8b2ebc4-123c-42bd-abd5-3bf1bff47ee0.xml, display.dxgi_ddi_arg_setdisplaymode, dxgiddi/DXGI_DDI_ARG_SETDISPLAYMODE
f1_keywords:
 - "dxgiddi/DXGI_DDI_ARG_SETDISPLAYMODE"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
- HeaderDef
api_location:
- dxgiddi.h
api_name:
- DXGI_DDI_ARG_SETDISPLAYMODE
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_SETDISPLAYMODE
---

# DXGI_DDI_ARG_SETDISPLAYMODE structure


## -description


The DXGI_DDI_ARG_SETDISPLAYMODE structure describes parameters for setting the display mode. 


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver sets the display mode. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the display device. 


### -field hResource

[in] A handle to the resource that contains the display surface.


### -field SubResourceIndex

[in] The zero-based index into the resource, which the handle in the <b>hResource</b> member specifies. The <b>SubResourceIndex</b> index indicates the display surface.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">SetDisplayModeDXGI</a>
 

 

