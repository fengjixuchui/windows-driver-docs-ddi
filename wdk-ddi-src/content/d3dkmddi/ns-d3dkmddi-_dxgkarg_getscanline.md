---
UID: NS:d3dkmddi._DXGKARG_GETSCANLINE
title: _DXGKARG_GETSCANLINE (d3dkmddi.h)
description: The DXGKARG_GETSCANLINE structure contains information about a video present target's vertical blanking status.
old-location: display\dxgkarg_getscanline.htm
ms.assetid: 92138511-46cf-4c8b-84d0-a11fe9208be5
ms.date: 05/10/2018
keywords: ["DXGKARG_GETSCANLINE structure"]
ms.keywords: "*INOUT_PDXGKARG_GETSCANLINE, DXGKARG_GETSCANLINE, DXGKARG_GETSCANLINE structure [Display Devices], DmStructs_9e2cdcde-c2ca-4474-9c96-ee66a80f0295.xml, _DXGKARG_GETSCANLINE, d3dkmddi/DXGKARG_GETSCANLINE, display.dxgkarg_getscanline"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
req.typenames: DXGKARG_GETSCANLINE
f1_keywords:
 - _DXGKARG_GETSCANLINE
 - d3dkmddi/_DXGKARG_GETSCANLINE
 - DXGKARG_GETSCANLINE
 - d3dkmddi/DXGKARG_GETSCANLINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_GETSCANLINE
---

# _DXGKARG_GETSCANLINE structure


## -description

The DXGKARG_GETSCANLINE structure contains information about a video present target's vertical blanking status.

## -struct-fields

### -field VidPnTargetId

[in] The identifier of a display adapter's video present target.

### -field InVerticalBlank

[out] A Boolean variable that receives <b>TRUE</b> if the video present target is in vertical blanking mode and <b>FALSE</b> if the video present target is not in vertical blanking mode.

### -field ScanLine

[out] The video present target's current scan line.

## -remarks

A video present path represents a connection between a video present source (view) and a video present target (output) on a display adapter. For more information about video present networks, paths, sources, and targets, see <a href="/windows-hardware/drivers/display/introduction-to-video-present-networks">Introduction to Video Present Networks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_getscanline">DxgkDdiGetScanLine</a>