---
UID: NS:d3d10umddi.D3D10_1_DDI_BLEND_DESC
title: D3D10_1_DDI_BLEND_DESC (d3d10umddi.h)
description: The D3D10_1_DDI_BLEND_DESC structure describes a blend state.
old-location: display\d3d10_1_ddi_blend_desc.htm
ms.assetid: e398b1a3-60bf-4a4a-b5c2-1dc11cf3dae1
ms.date: 05/10/2018
ms.keywords: D3D10_1_DDI_BLEND_DESC, D3D10_1_DDI_BLEND_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_088d7013-3c56-4bfc-8e68-250b8e020a52.xml, d3d10umddi/D3D10_1_DDI_BLEND_DESC, display.d3d10_1_ddi_blend_desc
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_1_DDI_BLEND_DESC is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
- D3D10_1_DDI_BLEND_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10_1_DDI_BLEND_DESC
---

# D3D10_1_DDI_BLEND_DESC structure


## -description


The D3D10_1_DDI_BLEND_DESC structure describes a blend state.


## -struct-fields




### -field AlphaToCoverageEnable

[in] A Boolean value that specifies whether transparency coverage is enabled. <b>TRUE</b> indicates transparency coverage is enabled; <b>FALSE</b> indicates transparency coverage is disabled. This member is relevant for multiple-sample antialiasing only.


### -field IndependentBlendEnable

[in] A Boolean value that specifies only whether the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize">CalcPrivateBlendStateSize(D3D10_1)</a> function replicated the first entry in the array that the <b>RenderTarget</b> member specifies to the other entries of that array. <b>TRUE</b> indicates the first entry was not replicated; <b>FALSE</b> indicates that the first entry in the array in the <b>RenderTarget</b> member is replicated to the other entries of the array. 


### -field RenderTarget

[in] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_ddi_render_target_blend_desc1">D3D10_DDI_RENDER_TARGET_BLEND_DESC1</a> structures that indicate the blend state for each associated render target.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize">CalcPrivateBlendStateSize(D3D10_1)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_1ddi_createblendstate">CreateBlendState(D3D10_1)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d10_ddi_blend">D3D10_DDI_BLEND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d10_ddi_blend_op">D3D10_DDI_BLEND_OP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_ddi_render_target_blend_desc1">D3D10_DDI_RENDER_TARGET_BLEND_DESC1</a>
 

 

