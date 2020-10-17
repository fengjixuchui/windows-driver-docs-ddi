---
UID: NC:d3dumddi.PFND3DDDI_SETCLIPPLANE
title: PFND3DDDI_SETCLIPPLANE (d3dumddi.h)
description: The SetClipPlane function sets a clip plane.
old-location: display\setclipplane.htm
tech.root: display
ms.assetid: 99edfc35-23a5-41e0-8705-7dffba564c10
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETCLIPPLANE callback function"]
ms.keywords: PFND3DDDI_SETCLIPPLANE, PFND3DDDI_SETCLIPPLANE callback, SetClipPlane, SetClipPlane callback function [Display Devices], UserModeDisplayDriver_Functions_695212ed-888d-40c9-8234-305373703b98.xml, d3dumddi/SetClipPlane, display.setclipplane
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
 - PFND3DDDI_SETCLIPPLANE
 - d3dumddi/PFND3DDDI_SETCLIPPLANE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetClipPlane
product:
 - Windows
---

# PFND3DDDI_SETCLIPPLANE callback function


## -description

The <i>SetClipPlane</i> function sets a clip plane.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setclipplane">D3DDDIARG_SETCLIPPLANE</a> structure that describes the clip plane to set.

## -returns

<i>SetClipPlane</i> returns S_OK or an appropriate error result if the clip plane is not successfully set.

## -remarks

The coefficients that are passed to <i>SetClipPlane</i> in the <b>Plane</b> array of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setclipplane">D3DDDIARG_SETCLIPPLANE</a> structure that is pointed to by <i>pData </i>are used in the general plane equation. For more information about the general plane equation, see the Remarks section of <b>D3DDDIARG_SETCLIPPLANE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setclipplane">D3DDDIARG_SETCLIPPLANE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>