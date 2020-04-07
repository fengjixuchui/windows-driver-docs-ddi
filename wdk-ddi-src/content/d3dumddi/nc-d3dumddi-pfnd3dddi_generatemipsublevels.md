---
UID: NC:d3dumddi.PFND3DDDI_GENERATEMIPSUBLEVELS
title: PFND3DDDI_GENERATEMIPSUBLEVELS (d3dumddi.h)
description: The GenerateMipSubLevels function regenerates the sublevels of a MIP-map texture.
old-location: display\generatemipsublevels.htm
tech.root: display
ms.assetid: 86567fc1-cf66-4709-a6e1-6b24408df963
ms.date: 05/10/2018
keywords: ["PFND3DDDI_GENERATEMIPSUBLEVELS callback function"]
ms.keywords: GenerateMipSubLevels, GenerateMipSubLevels callback function [Display Devices], PFND3DDDI_GENERATEMIPSUBLEVELS, PFND3DDDI_GENERATEMIPSUBLEVELS callback, UserModeDisplayDriver_Functions_795601cd-37d8-4268-8e41-38806c5961e6.xml, d3dumddi/GenerateMipSubLevels, display.generatemipsublevels
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/GenerateMipSubLevels"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - GenerateMipSubLevels
product:
 - Windows
---

# PFND3DDDI_GENERATEMIPSUBLEVELS callback function

## -description

The <i>GenerateMipSubLevels</i> function regenerates the sublevels of a MIP-map texture.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_generatemipsublevels">D3DDDIARG_GENERATEMIPSUBLEVELS</a> structure that describes how to generate the sublevels of a MIP-map texture.

## -returns

<i>GenerateMipSubLevels</i> returns S_OK or an appropriate error result if the sublevels of a MIP-map texture are not successfully generated.

## -remarks

After the user-mode display driver performs an operation that accesses only the top level of a MIP-map texture, the Microsoft Direct3D runtime calls the driver's <i>GenerateMipSubLevels</i> function to notify the driver to automatically regenerate the sublevels of the MIP-map texture by using a specific filter type.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_generatemipsublevels">D3DDDIARG_GENERATEMIPSUBLEVELS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

