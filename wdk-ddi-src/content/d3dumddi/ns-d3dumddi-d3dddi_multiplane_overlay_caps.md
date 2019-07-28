---
UID: NS:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_CAPS
title: D3DDDI_MULTIPLANE_OVERLAY_CAPS (d3dumddi.h)
description: Used by the user-mode display driver to specify overlay plane capabilities.
old-location: display\d3dddi_multiplane_overlay_caps.htm
tech.root: display
ms.assetid: 66365126-d7c3-4886-b14f-a94dc12c1626
ms.date: 05/10/2018
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_CAPS, D3DDDI_MULTIPLANE_OVERLAY_CAPS structure [Display Devices], d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_CAPS, display.d3dddi_multiplane_overlay_caps
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_CAPS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dumddi.h
api_name:
- D3DDDI_MULTIPLANE_OVERLAY_CAPS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_CAPS
---

# D3DDDI_MULTIPLANE_OVERLAY_CAPS structure


## -description


Used by the user-mode display driver to specify overlay plane capabilities.


## -struct-fields




### -field MaxPlanes

The maximum number of inputs, including the primary surface, to the display hardware that can be supported in the current mode. This value can change if the mode changes.

For example, if the hardware allows one overlay plane and one normal primary surface, the driver should set <b>MaxPlanes</b> to 2.


### -field NumCapabilityGroups

The number of different types of overlay planes that can be supported.

Here are 2 examples:

<ul>
<li>If the hardware supports 2 RGB-only planes with limited stretching capabilities, plus 2 YUV planes with more flexible stretching capabilities, then the driver should set <b>NumCapabilityGroups</b> to 2.</li>
<li>If the hardware supports one RGB-only plane with no stretching capabilities, plus 2 RGB-only planes with full  stretching capabilities, plus 2 RGB/YUV planes with full stretching capabilities, then the driver should set <b>NumCapabilityGroups</b> to 3.</li>
</ul>
