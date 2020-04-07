---
UID: NC:d3dkmddi.DXGKDDI_DESTROYOVERLAY
title: DXGKDDI_DESTROYOVERLAY (d3dkmddi.h)
description: The DxgkDdiDestroyOverlay function disables overlay hardware and deletes the specified overlay handle.
old-location: display\dxgkddidestroyoverlay.htm
ms.assetid: ea4672a2-ba21-42d4-9ff3-4fa611f86c90
ms.date: 05/10/2018
keywords: ["DXGKDDI_DESTROYOVERLAY callback function"]
ms.keywords: DXGKDDI_DESTROYOVERLAY, DXGKDDI_DESTROYOVERLAY callback, DmFunctions_e4fa2e3e-ac60-4235-92cc-77e71116a4d4.xml, DxgkDdiDestroyOverlay, DxgkDdiDestroyOverlay callback function [Display Devices], d3dkmddi/DxgkDdiDestroyOverlay, display.dxgkddidestroyoverlay
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdiDestroyOverlay"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiDestroyOverlay
product:
 - Windows
---

# DXGKDDI_DESTROYOVERLAY callback function

## -description

The <i>DxgkDdiDestroyOverlay</i> function disables overlay hardware and deletes the specified overlay handle.

## -parameters

### -param hOverlay

[in] A handle to the overlay to destroy. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createoverlay">DxgkDdiCreateOverlay</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hOverlay</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createoverlay">DXGKARG_CREATEOVERLAY</a> structure.

## -returns

<i>DxgkDdiDestroyOverlay</i> returns STATUS_SUCCESS, or an appropriate error result if overlay hardware is not successfully disabled.

## -remarks

<i>DxgkDdiDestroyOverlay</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createoverlay">DXGKARG_CREATEOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createoverlay">DxgkDdiCreateOverlay</a>

