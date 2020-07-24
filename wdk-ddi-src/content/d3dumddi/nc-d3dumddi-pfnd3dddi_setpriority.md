---
UID: NC:d3dumddi.PFND3DDDI_SETPRIORITY
title: PFND3DDDI_SETPRIORITY (d3dumddi.h)
description: The SetPriority function sets the eviction-from-memory priority for a managed texture.
old-location: display\setpriority.htm
tech.root: display
ms.assetid: 61ac2d28-7aed-4796-8d09-591db936013b
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETPRIORITY callback function"]
ms.keywords: PFND3DDDI_SETPRIORITY, PFND3DDDI_SETPRIORITY callback, SetPriority, SetPriority callback function [Display Devices], UserModeDisplayDriver_Functions_6e8f2a2a-f88b-45b6-9c59-b942cb44664b.xml, d3dumddi/SetPriority, display.setpriority
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
 - "d3dumddi/SetPriority"
 - "SetPriority"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetPriority
product:
 - Windows
---

# PFND3DDDI_SETPRIORITY callback function

## -description

The <i>SetPriority</i> function sets the eviction-from-memory priority for a managed texture.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setpriority">D3DDDIARG_SETPRIORITY</a> structure that specifies the priority level to set for the managed texture.

## -returns

<i>SetPriority</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The priority level is successfully set.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|

## -remarks

The Microsoft Direct3D runtime calls <i>SetPriority</i> to set the priority level for a resource. The user-mode display driver should translate the resource handle that is supplied in the <b>hResource</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setpriority">D3DDDIARG_SETPRIORITY</a> structure that is pointed to by <i>pData</i> to an allocation handle. After the driver makes this translation, the driver should pass the resulting handle in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setprioritycb">pfnSetPriorityCb</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setpriority">D3DDDIARG_SETPRIORITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setprioritycb">pfnSetPriorityCb</a>

