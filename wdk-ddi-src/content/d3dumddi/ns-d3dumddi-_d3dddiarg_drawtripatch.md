---
UID: NS:d3dumddi._D3DDDIARG_DRAWTRIPATCH
title: _D3DDDIARG_DRAWTRIPATCH (d3dumddi.h)
description: The D3DDDIARG_DRAWTRIPATCH structure describes a triangular patch to draw.
old-location: display\d3dddiarg_drawtripatch.htm
tech.root: display
ms.assetid: 296ed752-ddb6-41db-957f-606acc53b3b5
ms.date: 05/10/2018
keywords: ["D3DDDIARG_DRAWTRIPATCH structure"]
ms.keywords: D3DDDIARG_DRAWTRIPATCH, D3DDDIARG_DRAWTRIPATCH structure [Display Devices], UMDisplayDriver_param_Structs_e4f18b26-f2ae-46e2-af49-6ae55f79b2be.xml, _D3DDDIARG_DRAWTRIPATCH, d3dumddi/D3DDDIARG_DRAWTRIPATCH, display.d3dddiarg_drawtripatch
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
targetos: Windows
req.typenames: D3DDDIARG_DRAWTRIPATCH
f1_keywords:
 - _D3DDDIARG_DRAWTRIPATCH
 - d3dumddi/_D3DDDIARG_DRAWTRIPATCH
 - D3DDDIARG_DRAWTRIPATCH
 - d3dumddi/D3DDDIARG_DRAWTRIPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_DRAWTRIPATCH
---

# _D3DDDIARG_DRAWTRIPATCH structure


## -description

The D3DDDIARG_DRAWTRIPATCH structure describes a triangular patch to draw.

## -struct-fields

### -field Handle

[in] The handle to the patch surface.

## -remarks

The <b>Handle</b> member refers to the patch surface, so that the next time the patch surface is drawn, the Microsoft Direct3D runtime is not required to re-specify the D3DTRIPATCH_INFO data structure for the patch surface. The user-mode display driver can precompute and cache forward-difference coefficients and any other information, which allows subsequent calls to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawtripatch">DrawTriPatch</a> function that use the same handle to run more efficiently.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawtripatch">DrawTriPatch</a>

