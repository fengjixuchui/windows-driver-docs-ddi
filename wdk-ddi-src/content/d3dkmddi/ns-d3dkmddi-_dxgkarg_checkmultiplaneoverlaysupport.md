---
UID: NS:d3dkmddi._DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
title: _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT (d3dkmddi.h)
description: Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport function to check details on hardware support for multiplane overlays.
old-location: display\dxgkarg_checkmultiplaneoverlaysupport.htm
ms.assetid: BAFC7DD1-56F8-47CE-8914-54531BBC3165
ms.date: 05/10/2018
keywords: ["DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure"]
ms.keywords: "*IN_OUT_PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure [Display Devices], PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure pointer [Display Devices], _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, d3dkmddi/DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, d3dkmddi/PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, display.dxgkarg_checkmultiplaneoverlaysupport"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
tech.root: display
req.typenames: DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
f1_keywords:
 - _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
 - d3dkmddi/_DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
 - DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
 - d3dkmddi/DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
---

# _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure

> [!NOTE] This structure has been replaced by [DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3](ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport3.md)


## -description

Used in a call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport">DxgkDdiCheckMultiPlaneOverlaySupport</a> function to check details on hardware support for multiplane overlays.

## -struct-fields

### -field PlaneCount

The number of overlay planes that the hardware supports.

### -field pPlanes

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_check_multiplane_overlay_support_plane">DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE</a> structure that specifies support attributes that the hardware provides for multiplane overlays.

### -field Supported

<b>TRUE</b> if the hardware supports multiplane overlays, otherwise <b>FALSE</b>.

### -field ReturnInfo

Specifies limitations on hardware support of multiplane overlays.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_check_multiplane_overlay_support_plane">DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport">DxgkDdiCheckMultiPlaneOverlaySupport</a>