---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_COLOR
title: D3D11_1DDI_VIDEO_COLOR (d3d10umddi.h)
description: Defines a color value for Microsoft Direct3D 11 video.
old-location: display\d3d11_1ddi_video_color.htm
ms.assetid: 200ca1d5-cbfd-4ad8-aa41-8238ea7ea5cf
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_VIDEO_COLOR, D3D11_1DDI_VIDEO_COLOR structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_COLOR, display.d3d11_1ddi_video_color
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_VIDEO_COLOR"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_VIDEO_COLOR
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_COLOR
---

# D3D11_1DDI_VIDEO_COLOR structure


## -description


Defines a color value for Microsoft Direct3D 11 video.


## -struct-fields




### -field YCbCr

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color_ycbcra">D3D11_1DDI_VIDEO_COLOR_YCbCrA</a> structure that contains a YCbCr color value.


### -field RGBA

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color_rgba">D3D11_1DDI_VIDEO_COLOR_RGBA</a> structure that contains an RGB color value.


## -remarks



The anonymous union can represent both RGB and YCbCr colors. The interpretation of the union depends on the context.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color_rgba">D3D11_1DDI_VIDEO_COLOR_RGBA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color_ycbcra">D3D11_1DDI_VIDEO_COLOR_YCbCrA</a>
 

 

