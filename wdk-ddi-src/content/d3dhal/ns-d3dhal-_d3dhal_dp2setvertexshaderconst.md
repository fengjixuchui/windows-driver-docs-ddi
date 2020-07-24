---
UID: NS:d3dhal._D3DHAL_DP2SETVERTEXSHADERCONST
title: _D3DHAL_DP2SETVERTEXSHADERCONST (d3dhal.h)
description: DirectX 8.0 and later versions only. The D3DHAL_DP2SETVERTEXSHADERCONST structure is used to set one or more of the vertex shader constant registers when the D3DDP2OP_SETVERTEXSHADERCONST opcode is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setvertexshaderconst.htm
tech.root: display
ms.assetid: f3973564-8739-4bf7-b9f7-e5792018b98d
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2SETVERTEXSHADERCONST structure"]
ms.keywords: "*LPD3DHAL_DP2SETVERTEXSHADERCONST, *LPD3DHAL_DP2SETVERTEXSHADERCONSTB, *LPD3DHAL_DP2SETVERTEXSHADERCONSTI, D3DHAL_DP2SETVERTEXSHADERCONST, D3DHAL_DP2SETVERTEXSHADERCONST structure [Display Devices], D3DHAL_DP2SETVERTEXSHADERCONSTB, D3DHAL_DP2SETVERTEXSHADERCONSTI, LPD3DHAL_DP2SETVERTEXSHADERCONST, LPD3DHAL_DP2SETVERTEXSHADERCONST structure pointer [Display Devices], _D3DHAL_DP2SETVERTEXSHADERCONST, d3dhal/D3DHAL_DP2SETVERTEXSHADERCONST, d3dhal/LPD3DHAL_DP2SETVERTEXSHADERCONST, d3dstrct_5d02ceb6-1d80-4586-a256-ca56ca51a101.xml, display.d3dhal_dp2setvertexshaderconst"
f1_keywords:
 - "d3dhal/D3DHAL_DP2SETVERTEXSHADERCONST"
 - "D3DHAL_DP2SETVERTEXSHADERCONST"
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- d3dhal.h
api_name:
- D3DHAL_DP2SETVERTEXSHADERCONST
targetos: Windows
req.typenames: D3DHAL_DP2SETVERTEXSHADERCONST
---

# _D3DHAL_DP2SETVERTEXSHADERCONST structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2SETVERTEXSHADERCONST structure is used to set one or more of the vertex shader constant registers when the D3DDP2OP_SETVERTEXSHADERCONST opcode is received by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.


## -struct-fields




### -field dwRegister

Specifies the index of the first vertex shader constant to have its value sent.


### -field dwCount

Specifies the number of constant registers to set and, therefore, the number of four element, single precision float vectors to read from the DP2 stream.


## -remarks



A start register and register count are given. One or more vectors of four single precision floating-point values immediately follow the D3DHAL_DP2SETVERTEXSHADERCONST data structure in the DP2 stream.

The runtime validates that the range of registers specified is legal given the level of vertex shader support reported to the driver. Furthermore, if the driver does not support any form of programmable vertex processing the runtime does not send this token to the driver.




## -see-also




D3DDP2OP_SETVERTEXSHADERCONST



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2createvertexshader">D3DHAL_DP2CREATEVERTEXSHADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2vertexshader">D3DHAL_DP2VERTEXSHADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

