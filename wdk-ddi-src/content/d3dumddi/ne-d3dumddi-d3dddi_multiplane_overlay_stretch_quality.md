---
UID: NE:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY
title: D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY (d3dumddi.h)
description: Identifies filtering processes that the hardware should perform when it stretches or shrinks multiplane overlay data.
old-location: display\d3dddi_multiplane_overlay_stretch_quality.htm
tech.root: display
ms.assetid: 531F541F-4F53-4FAC-A1B7-B51467F34833
ms.date: 05/10/2018
keywords: ["D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY enumeration"]
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY, D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY enumeration [Display Devices], D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR, D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH, display.d3dddi_multiplane_overlay_stretch_quality
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY
f1_keywords:
 - D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY
 - d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY
---

# D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY enumeration


## -description

Identifies filtering processes that the hardware should perform when it stretches or shrinks multiplane overlay data.

## -enum-fields

### -field D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_BILINEAR

When the hardware stretches or shrinks the data, it should perform bilinear filtering. If the hardware lacks enough resources to perform bilinear shrinking, the user-mode display driver can use point sampling.

### -field D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY_HIGH

When the hardware stretches or shrinks the data, it should perform the highest quality filtering that it supports.

