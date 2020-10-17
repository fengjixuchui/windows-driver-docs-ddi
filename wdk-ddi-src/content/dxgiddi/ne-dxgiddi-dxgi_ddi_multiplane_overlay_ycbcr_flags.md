---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
title: DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS (dxgiddi.h)
description: Identifies YUV range and conversion info that describes a multiplane overlay.
old-location: display\dxgi_ddi_multiplane_overlay_ycbcr_flags.htm
tech.root: display
ms.assetid: fa915ec0-167f-441c-b2de-0ae2b852c432
ms.date: 05/10/2018
keywords: ["DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS enumeration"]
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS enumeration [Display Devices], DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC, display.dxgi_ddi_multiplane_overlay_ycbcr_flags, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
f1_keywords:
 - DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
 - dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dxgiddi.h
api_name:
 - DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
---

# DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS enumeration


## -description

Identifies YUV range and conversion info that describes a multiplane overlay.

## -enum-fields

### -field DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE

YUV values range from 16 to 235, inclusive, instead of the default range of 0 to 255, inclusive.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709

YUV values should be converted using the BT.709 standard, instead of the default BT.601 conversion.

### -field DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC

YUV values contain xvYCC data, instead of conventional YCbCr data.

## -remarks

For more info on how YUV ranges are defined and converted, see <a href="/windows-hardware/drivers/display/yuv-format-ranges">YUV format ranges in Windows 8.1</a>.