---
UID: NC:d3dkmddi.DXGKCB_DESTROYCONTEXTALLOCATION
title: DXGKCB_DESTROYCONTEXTALLOCATION (d3dkmddi.h)
description: Called by a WDDM 1.2 or later display miniport driver to free a resource that was previously allocated for a GPU or device-specific context.
old-location: display\dxgkcbdestroycontextallocation.htm
ms.assetid: f613e019-0b6d-43fc-a802-a6cd3803a00d
ms.date: 05/10/2018
ms.keywords: DXGKCB_DESTROYCONTEXTALLOCATION, DXGKCB_DESTROYCONTEXTALLOCATION callback, DxgkCbDestroyContextAllocation, DxgkCbDestroyContextAllocation callback function [Display Devices], d3dkmddi/DxgkCbDestroyContextAllocation, display.dxgkcbdestroycontextallocation
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DxgkCbDestroyContextAllocation"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3dkmddi.h
api_name:
- DxgkCbDestroyContextAllocation
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_DESTROYCONTEXTALLOCATION callback function


## -description


Called by a WDDM 1.2 or later display miniport driver to free a resource that was previously allocated for a GPU or device-specific context.


## -parameters




### -param hAdapter

[in] A handle to the graphics adapter for which the allocation was created. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.



### -param hAllocation

[in] A handle that was assigned by the DirectX graphics subsystem to the allocation. The display miniport driver receives the handle from the <b>hAllocation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkargcb_createcontextallocation">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure in the call to the<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_createcontextallocation">DxgkCbCreateContextAllocation</a> function.


## -returns



<i>DxgkCbDestroyContextAllocation</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



The driver allocates  context resources by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_createcontextallocation">DxgkCbCreateContextAllocation</a>.

After the display miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_createcontextallocation">DxgkCbCreateContextAllocation</a> to allocate a context resource, it can call <i>DxgkCbDestroyContextAllocation</i> to free the resource at any time.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkargcb_createcontextallocation">DXGKARGCB_CREATECONTEXTALLOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_createcontextallocation">DxgkCbCreateContextAllocation</a>
 

 

