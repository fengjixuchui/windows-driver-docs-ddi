---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING (d3d10umddi.h)
description: D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING is used by the user-mode driver to recommend downsampling parameters that can be used to decode the stream in real-time.
old-location: display\d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.htm
ms.assetid: 5BC38128-8866-48C9-B5C5-4D6B6DB793E0
ms.date: 05/10/2018
keywords: ["D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING structure"]
ms.keywords: D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING, display.d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling
f1_keywords:
 - "d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING structure


## -description


<b>D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</b> is used by the user-mode driver to recommend downsampling parameters that can be used to decode the stream in real-time.


## -struct-fields




### -field pInputDesc

Contains the decode profile used and the resolution and format of the reference frames.  This is the resolution/format to be downsampled (e.g. 4K, DXGI_FORMAT_P010).


### -field InputColorSpace

Contains the color space information of the reference frame data.


### -field pInputConfig

Contains the configuration data associated with the decode profile.


### -field pFrameRate

Contains the frame rate of the video content.


### -field pOutputDesc

The driver returns the recommended resolution and the format of the output/display frames.  



<div class="alert"><b>Note</b>  The decode profile (<b>Guid</b>) member of <b>pOutputDesc</b> can be ignored.
</div>
<div> </div>

### -field OutputColorSpace

The driver returns the recommended color space information of the display frame data.


## -remarks



The driver recommends the down sample parameters such that the video stream can be decoded in real-time. If no down sample solution exists that can result in real-time decode, the driver should recommend the configuration that is closest to the real-time solution. 



