---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_SCALE_SUPPORT_0022
title: D3D12DDI_VIDEO_SCALE_SUPPORT_0022 (d3d12umddi.h)
description: Describes a supported range of output sizes for a scaler.
old-location: display\d3d12ddi_video_scale_support.htm
ms.assetid: 70FFDE9E-2029-4C84-9DEE-C2E81FEE5590
ms.date: 05/10/2018
keywords: ["D3D12DDI_VIDEO_SCALE_SUPPORT_0022 structure"]
ms.keywords: D3D12DDI_VIDEO_SCALE_SUPPORT_0022, D3D12DDI_VIDEO_SCALE_SUPPORT_0022 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_0022, display.d3d12ddi_video_scale_support
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_0022"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
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
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_SCALE_SUPPORT_0022
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_SCALE_SUPPORT_0022
---

# D3D12DDI_VIDEO_SCALE_SUPPORT_0022 structure


## -description


Describes a supported range of output sizes for a scaler.


## -struct-fields




### -field MaxOutputWidth

The largest output width that can be scaled to.  The largest value allowed is <b>D3D12_REQ_TEXTURE2D_U_OR_V_DIMENSION</b>, which is 16384.


### -field MaxOutputHeight

The largest output height that can be scaled to.  The largest value allowed is <b>D3D12_REQ_TEXTURE2D_U_OR_V_DIMENSION</b>, which is 16384.


### -field MinOutputWidth

The smallest output width that can be scaled to.  The smallest allowed value is 1.


### -field MinOutputHeight

The smallest output height that can be scaled to.  The smallest allowed value is 1.


### -field Flags

*ScaleSupportFlags*

Flags that indicated level of scale support. For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_scale_support_flags_0022">D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS</a> enumeration. 


## -remarks



By default, supported indicates that all possible output size combinations that exist between the maximum  size and minimum size for the extent, inclusive, are supported.  The values in the <i>ScaleSupportFlags</i> value may add additional restrictions.


When scaling is not supported, the maximum and maximum sizes should both be set to the input size and no flags specified.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_scale_support_flags_0022">D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS</a>
 

 

