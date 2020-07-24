---
UID: NC:d3dumddi.PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB
title: PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB (d3dumddi.h)
description: Copies content from a source multiplane overlay allocation to a destination allocation. Can be called by Windows Display Driver Model (WDDM) 1.3 or later user-mode display drivers.
old-location: display\pfnpresentmultiplaneoverlaycb_d3d.htm
tech.root: display
ms.assetid: f355c29a-8a8d-46aa-b3b3-c93c0afef266
ms.date: 05/10/2018
keywords: ["PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB callback function"]
ms.keywords: PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB, d3dumddi/pfnPresentMultiPlaneOverlayCb, display.pfnpresentmultiplaneoverlaycb_d3d, pfnPresentMultiPlaneOverlayCb, pfnPresentMultiPlaneOverlayCb (D3D) callback, pfnPresentMultiPlaneOverlayCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - "d3dumddi/pfnPresentMultiPlaneOverlayCb"
 - "pfnPresentMultiPlaneOverlayCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dumddi.h
api_name:
 - pfnPresentMultiPlaneOverlayCb
product:
 - Windows
---

# PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB callback function

## -description

Copies content from a source multiplane overlay allocation to a destination allocation. Can be called by Windows Display Driver Model (WDDM) 1.3 or later user-mode display drivers.

## -parameters

### -param hDevice

A handle to a display device (graphics context).

### -param Arg2

*pPresent* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_presentmultiplaneoverlay">D3DDDICB_PRESENTMULTIPLANEOVERLAY</a> structure that describes the source and destination allocations that content is copied from and to.

## -returns

Returns one of these values:

|Return code|Description|
|--- |--- |
|S_OK|Content was successfully copied.|
|E_OUTOFMEMORY|The function could not complete because of insufficient memory.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|

## -remarks

The user-mode display driver should call this function only after it has successfully processed a call by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentmultiplaneoverlay">pfnPresentMultiplaneOverlay (D3D)</a> function.

<div class="alert"><b>Note</b>  When the display driver calls <b>pfnPresentMultiPlaneOverlayCb (D3D)</b>, it must maintain the same order of allocations in the <b>AllocationInfo</b> array member of the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_presentmultiplaneoverlay">D3DDDICB_PRESENTMULTIPLANEOVERLAY</a> structure as it received from the Microsoft Direct3D runtime when the runtime called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentmultiplaneoverlay">pfnPresentMultiplaneOverlay (D3D)</a>.<p class="note">For example, the allocation handle in index 1 of <b>AllocationInfo</b> must represent the same resource that was passed to the driver in index 1 of the <i>pPresentPlanes</i> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddiarg_presentmultiplaneoverlay">D3DDDIARG_PRESENTMULTIPLANEOVERLAY</a> structure used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentmultiplaneoverlay">pfnPresentMultiplaneOverlay (D3D)</a>.

</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddiarg_presentmultiplaneoverlay">D3DDDIARG_PRESENTMULTIPLANEOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicb_presentmultiplaneoverlay">D3DDDICB_PRESENTMULTIPLANEOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentmultiplaneoverlay">pfnPresentMultiplaneOverlay (D3D)</a>

