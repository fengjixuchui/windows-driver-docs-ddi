---
UID: NC:d3d10umddi.PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
title: PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE (d3d10umddi.h)
description: The CalcPrivateShaderResourceViewSize(D3D10_1) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.
old-location: display\calcprivateshaderresourceviewsize_d3d10_1_.htm
ms.assetid: 310adb3e-1af4-430e-ba50-bd145ffda361
ms.date: 05/10/2018
keywords: ["PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function"]
ms.keywords: CalcPrivateShaderResourceViewSize_d3d10_1_, CalcPrivateShaderResourceViewSize_d3d10_1_ callback function [Display Devices], PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE, PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback, UserModeDisplayDriverDx10_Functions_dc420977-d68c-4e07-b134-fc5540a96e7b.xml, d3d10umddi/CalcPrivateShaderResourceViewSize_d3d10_1_, display.calcprivateshaderresourceviewsize_d3d10_1_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateShaderResourceViewSize(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
 - "d3d10umddi/CalcPrivateShaderResourceViewSize_d3d10_1_"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CalcPrivateShaderResourceViewSize_d3d10_1_
product:
 - Windows
---

# PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function

## -description

The <b>CalcPrivateShaderResourceViewSize(D3D10_1)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.

## -parameters

### -param Arg1

*hDevice* [in] 

A handle to the display device (graphics context).

### -param Arg2

*pCreateShaderResourceView* [in] 

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddiarg_createshaderresourceview">D3D10_1DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

<b>CalcPrivateShaderResourceViewSize(D3D10_1)</b> returns the size of the memory region that the driver requires for creating a shader resource view.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddiarg_createshaderresourceview">D3D10_1DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddi_devicefuncs">D3D10_1DDI_DEVICEFUNCS</a>

