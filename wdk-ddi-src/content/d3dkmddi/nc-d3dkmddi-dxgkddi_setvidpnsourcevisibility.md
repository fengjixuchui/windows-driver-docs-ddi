---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEVISIBILITY
title: DXGKDDI_SETVIDPNSOURCEVISIBILITY (d3dkmddi.h)
description: The DxgkDdiSetVidPnSourceVisibility function programs the video output codec that is associated with a specified video present source to either start scanning or stop scanning the source's primary surface.
old-location: display\dxgkddisetvidpnsourcevisibility.htm
ms.assetid: c94473b4-b898-456d-944d-8879adea16d1
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SETVIDPNSOURCEVISIBILITY, DXGKDDI_SETVIDPNSOURCEVISIBILITY callback, DmFunctions_6a3bb1aa-8bc1-4672-8028-ea3299809a37.xml, DxgkDdiSetVidPnSourceVisibility, DxgkDdiSetVidPnSourceVisibility callback function [Display Devices], d3dkmddi/DxgkDdiSetVidPnSourceVisibility, display.dxgkddisetvidpnsourcevisibility
ms.topic: callback
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
 - "d3dkmddi/DxgkDdiSetVidPnSourceVisibility"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiSetVidPnSourceVisibility
product:
 - Windows
---

# DXGKDDI_SETVIDPNSOURCEVISIBILITY callback function

## -description

The <i>DxgkDdiSetVidPnSourceVisibility</i> function programs the video output codec that is associated with a specified video present source to either start scanning or stop scanning the source's primary surface.

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pSetVidPnSourceVisibility

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_setvidpnsourcevisibility">DXGKARG_SETVIDPNSOURCEVISIBILITY</a> structure that contains function arguments.

## -returns

<i>DxgkDdiSetVidPnSourceVisibility </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## -remarks

See requirements on calling this function with multiplane overlays in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/multiplane-overlay-vidpn-presentation">Multiplane overlay VidPN presentation</a>.

<i>DxgkDdiSetVidPnSourceVisibility</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560767(v=vs.85)">DxgkDdiSetVidPnSourceAddress</a>

