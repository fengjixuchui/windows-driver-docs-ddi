---
UID: NC:d3d10umddi.PFND3D11DDI_SETRENDERTARGETS
title: PFND3D11DDI_SETRENDERTARGETS (d3d10umddi.h)
description: The SetRenderTargets(D3D11) function sets render target surfaces.
old-location: display\setrendertargets_d3d11_.htm
ms.assetid: cfe5f570-4e53-43ee-942d-56da8dfcfe80
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_SETRENDERTARGETS callback function"]
ms.keywords: PFND3D11DDI_SETRENDERTARGETS, PFND3D11DDI_SETRENDERTARGETS callback, SetRenderTargets, SetRenderTargets callback function [Display Devices], UserModeDisplayDriverDx11_Functions_a24d5500-fe0a-4d17-a3fb-acb6ed9e4698.xml, d3d10umddi/SetRenderTargets, display.setrendertargets_d3d11_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: SetRenderTargets(D3D11) is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_SETRENDERTARGETS
 - d3d10umddi/PFND3D11DDI_SETRENDERTARGETS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - SetRenderTargets
---

# PFND3D11DDI_SETRENDERTARGETS callback function


## -description

The <i>SetRenderTargets(D3D11)</i> function sets render target surfaces.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*phRenderTargetView* [in]

An array of handles to the render target view objects to set. Note that some handle values can be <b>NULL</b>.

### -param NumRTVs 

[in]
The number of elements in the array that <i>phRenderTargetView</i> specifies for the render target views (RTVs) to set.

### -param ClearSlots

*RTVNumbertoUnbind* [in]

The number of render target view (RTV) objects to unbind (that is, those render target view objects that are previously set but should be no longer set).

### -param Arg5

*hDepthStencilView* [in]

A handle to the depth-stencil buffer to set.

### -param Arg6

*phUnorderedAccessView* [in]

An array of handles to the unordered access view (UAV) objects.

### -param Arg7

*pUAVInitialCounts* [in]

An array of append and consume buffer offsets. <i>pUAV</i> is only relevant for unordered access views (UAVs)  of the <i>phUnorderedAccessView</i> array that were created with either <b>D3D11_DDI_BUFFER_UAV_FLAG_APPEND</b>  or <b>D3D11_DDI_BUFFER_UAV_FLAG_COUNTER</b> set in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a> structure when the UAV was created; otherwise, the argument is ignored. If an element in this array is set to -1, the current offset for that append and consume buffer should be kept. Any other value causes the driver to set the hidden counter for that UAV append and consume buffer.

### -param UAVStartSlot

Indicates the start element, in the array of bind points, where the passed unordered access view (UAV) array is going to be applied. <i>UAVIndex</i> should be at least as great as  the <i>NumRTVs</i> parameter.

<div class="alert"><b>Note</b>  Only one shared set of binding points exists for render target views (RTVs) and UAVs. RTVs are bound first, followed by UAVs.</div>
<div> </div>

### -param NumUAVs 

[in]
The number of unordered access view objects (UAVs) to set.

### -param UAVRangeStart

The first unordered access view object (UAV) in the set of all updated UAVs (which includes <b>NULL</b> bindings).

### -param UAVRangeSize

The number of unordered access view objects (UAVs) in the set of all updated UAVs (which includes <b>NULL</b> bindings). 

<div class="alert"><b>Note</b>  The parameters <i>UAVNumberUpdated</i> and  <i>UAVFirsttoSet</i> specify which range, in the  UAVs array, contains changes in relation to the state previously bound. Notice that points in the range could be unchanged. Also, update range indexing is not different from other parameters. For example, <i>UAVFirsttoSet</i>      starts at 0 as the first element of the shared render target view (RTV) and UAV bound space. This parameter is a convenience that reveals the span of what actually changed given that the Direct3D DDI always binds everything (including what has not changed).</div>
<div> </div>

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <i>SetRenderTargets(D3D11)</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_buffer_unorderedaccessview">D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

