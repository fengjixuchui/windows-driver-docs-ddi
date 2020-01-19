---
UID: NC:d3dumddi.PFND3DDDI_SETINDICES
title: PFND3DDDI_SETINDICES (d3dumddi.h)
description: The SetIndices function sets the current index buffer.
old-location: display\setindices.htm
tech.root: display
ms.assetid: 5348b3f9-78c5-4915-ba68-296d6f9f916c
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETINDICES, PFND3DDDI_SETINDICES callback, SetIndices, SetIndices callback function [Display Devices], UserModeDisplayDriver_Functions_c51c5796-e271-4b76-a013-88038767d356.xml, d3dumddi/SetIndices, display.setindices
ms.topic: callback
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
 - "d3dumddi/SetIndices"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetIndices
product:
 - Windows
---

# PFND3DDDI_SETINDICES callback function

## -description

The <i>SetIndices</i> function sets the current index buffer.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setindices">D3DDDIARG_SETINDICES</a> structure that describes parameters for setting the current index buffer.

## -returns

<i>SetIndices</i> returns S_OK or an appropriate error result if the index buffer is not successfully set.

## -remarks

The Microsoft Direct3D runtime supplies a handle value of zero in the <b>hIndexBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setindices">D3DDDIARG_SETINDICES</a> structure that is pointed to by the <i>pData</i> parameter to clear the current index buffer. The driver should handle subsequent attempts to draw indexed primitives (before a new current index buffer is established) so that a crash does not occur. The debug version of your driver should display informative messages to the debug output stream when this error condition is detected.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setindices">D3DDDIARG_SETINDICES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

