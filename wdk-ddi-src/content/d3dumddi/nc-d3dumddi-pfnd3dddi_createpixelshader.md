---
UID: NC:d3dumddi.PFND3DDDI_CREATEPIXELSHADER
title: PFND3DDDI_CREATEPIXELSHADER (d3dumddi.h)
description: The CreatePixelShader function converts pixel shader code into a hardware-specific format and associates this code with a shader handle.
old-location: display\createpixelshader.htm
tech.root: display
ms.assetid: b80a1823-6d91-440f-89e4-f7248579cc8f
ms.date: 05/10/2018
ms.keywords: CreatePixelShader, CreatePixelShader callback function [Display Devices], PFND3DDDI_CREATEPIXELSHADER, PFND3DDDI_CREATEPIXELSHADER callback, UserModeDisplayDriver_Functions_4e9d378f-d5aa-4b5d-9a66-ff2dd2f8fae8.xml, d3dumddi/CreatePixelShader, display.createpixelshader
ms.topic: callback
f1_keywords:
 - "d3dumddi/CreatePixelShader"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- CreatePixelShader
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATEPIXELSHADER callback function


## -description


The <b>CreatePixelShader</b> function converts pixel shader code into a hardware-specific format and associates this code with a shader handle.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param Arg2

*pCode* [in]

An array of CONST UINT tokens that make up the pixel shader code.

### -param Arg3

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createpixelshader">D3DDDIARG_CREATEPIXELSHADER</a> structure that retrieves the shader handle that is associated with the pixel shader code that is specified by <b>pCode</b>.


## -returns



<b>CreatePixelShader</b> returns S_OK or an appropriate error result if the pixel shader code object is not successfully created.




## -remarks



For more information about programming shader assemblers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/processing-shader-codes">Processing Shader Codes</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createpixelshader">D3DDDIARG_CREATEPIXELSHADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

