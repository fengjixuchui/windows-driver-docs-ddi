---
UID: NS:d3d10umddi.D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW
title: D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW (d3d10umddi.h)
description: The D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW structure describes a one-dimensional texture (1-D) that is used to create a depth stencil view in a call to the CreateDepthStencilView function.
old-location: display\d3d10ddiarg_tex1d_depthstencilview.htm
ms.assetid: 313e616c-12e3-4493-9c49-e79232bbf031
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW, D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_5d65c450-41df-45d9-9bdd-9ccb9890161a.xml, d3d10umddi/D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW, display.d3d10ddiarg_tex1d_depthstencilview
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW"
req.header: d3d10umddi.h
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
- d3d10umddi.h
api_name:
- D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW
---

# D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW structure


## -description


The D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW structure describes a one-dimensional texture (1-D) that is used to create a depth stencil view in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview">CreateDepthStencilView</a> function. 


## -struct-fields




### -field MipSlice

[in] The identifier of the MIP-map slice. 


### -field FirstArraySlice

[in] The identifier of the first array slice. 


### -field ArraySize

[in] The number of array slices for the texture. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize">CalcPrivateDepthStencilViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview">CreateDepthStencilView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdepthstencilview">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>
 

 

