---
UID: NC:d3d10umddi.PFND3D10DDI_RELOCATEDEVICEFUNCS
title: PFND3D10DDI_RELOCATEDEVICEFUNCS (d3d10umddi.h)
description: The RelocateDeviceFuncs function notifies the user-mode display driver about the new location of the driver function table.
old-location: display\relocatedevicefuncs.htm
ms.assetid: 3932a2a1-7b1d-4921-bd4a-905b44166091
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_RELOCATEDEVICEFUNCS callback function"]
ms.keywords: PFND3D10DDI_RELOCATEDEVICEFUNCS, PFND3D10DDI_RELOCATEDEVICEFUNCS callback, RelocateDeviceFuncs, RelocateDeviceFuncs callback function [Display Devices], UserModeDisplayDriverDx10_Functions_01a40916-8ba8-4e29-87d7-32e9c3fe337f.xml, d3d10umddi/RelocateDeviceFuncs, display.relocatedevicefuncs
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/RelocateDeviceFuncs"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - RelocateDeviceFuncs
product:
 - Windows
---

# PFND3D10DDI_RELOCATEDEVICEFUNCS callback function

## -description

The <i>RelocateDeviceFuncs</i> function notifies the user-mode display driver about the new location of the driver function table.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pDeviceFunctions* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver.

## -remarks


The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.


A user-mode display driver can use the <i>RelocateDeviceFuncs</i> function to replace function pointers in the driver function table.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

