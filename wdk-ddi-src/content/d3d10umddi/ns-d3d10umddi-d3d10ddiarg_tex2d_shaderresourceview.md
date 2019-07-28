---
UID: NS:d3d10umddi.D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW
title: D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW (d3d10umddi.h)
description: The D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW structure describes a two-dimensional (2-D) texture that is used to create a shader resource view in a call to the CreateShaderResourceView function.
old-location: display\d3d10ddiarg_tex2d_shaderresourceview.htm
ms.assetid: 2282d08e-e192-4a0f-972b-1441cea1fe7d
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW, D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_ebe6122b-f1bb-4f9d-b677-c721643fe227.xml, d3d10umddi/D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW, display.d3d10ddiarg_tex2d_shaderresourceview
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW"
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
- D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW
---

# D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW structure


## -description


The D3D10DDIARG_TEX2D_SHADERRESOURCEVIEW structure describes a two-dimensional (2-D) texture that is used to create a shader resource view in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview">CreateShaderResourceView</a> function. 


## -struct-fields




### -field MostDetailedMip

[in] The identifier of the most detailed MIP-map. 


### -field FirstArraySlice

[in] The identifier of the first array slice. 


### -field MipLevels

[in] The number of MIP-map levels for the texture. 


### -field ArraySize

[in] The number of array slices for the texture. 


## -remarks



If the <b>MipLevels</b> member is set to -1, the MIP-maps in the texture start from the MIP-map that is set in the <b>MostDetailedMip</b> member. 

If the <b>ArraySize</b> member is set to -1, the array slices in the texture start from the array slice that is set in <b>FirstArraySlice</b> member. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview">CreateShaderResourceView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createshaderresourceview">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>
 

 

