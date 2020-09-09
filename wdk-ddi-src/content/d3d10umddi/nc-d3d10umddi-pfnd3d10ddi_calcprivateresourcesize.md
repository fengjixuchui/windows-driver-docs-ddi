---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATERESOURCESIZE
title: PFND3D10DDI_CALCPRIVATERESOURCESIZE (d3d10umddi.h)
description: The CalcPrivateResourceSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory).
old-location: display\calcprivateresourcesize.htm
ms.assetid: 2c4eb002-4788-46ab-92b9-3bb2dcb44ee3
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CALCPRIVATERESOURCESIZE callback function"]
ms.keywords: CalcPrivateResourceSize, CalcPrivateResourceSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATERESOURCESIZE, PFND3D10DDI_CALCPRIVATERESOURCESIZE callback, UserModeDisplayDriverDx10_Functions_bc7bb9a2-6fe2-49fb-b7d2-81297a828418.xml, d3d10umddi/CalcPrivateResourceSize, display.calcprivateresourcesize
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
 - PFND3D10DDI_CALCPRIVATERESOURCESIZE
 - d3d10umddi/PFND3D10DDI_CALCPRIVATERESOURCESIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateResourceSize
product:
 - Windows
---

# PFND3D10DDI_CALCPRIVATERESOURCESIZE callback function


## -description

The <b>CalcPrivateResourceSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory).

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateResource* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateResourceSize</b> returns the size of the memory region that the driver requires for creating resources.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>

