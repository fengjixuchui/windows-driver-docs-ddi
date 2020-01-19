---
UID: NE:dxva._DXVA_VideoProcessCaps
title: _DXVA_VideoProcessCaps (dxva.h)
description: The DXVA_VideoProcessCaps enumeration identifies operations that can be performed concurrently with the requested deinterlace.
old-location: display\dxva_videoprocesscaps.htm
tech.root: display
ms.assetid: 225da110-cd59-4803-bde8-26e275b3ddbd
ms.date: 05/10/2018
ms.keywords: DXVA_VideoProcessCaps, DXVA_VideoProcessCaps enumeration [Display Devices], DXVA_VideoProcess_AlphaBlend, DXVA_VideoProcess_AlphaBlendExtended, DXVA_VideoProcess_None, DXVA_VideoProcess_StretchX, DXVA_VideoProcess_StretchY, DXVA_VideoProcess_SubRects, DXVA_VideoProcess_SubStreams, DXVA_VideoProcess_SubStreamsExtended, DXVA_VideoProcess_YUV2RGB, DXVA_VideoProcess_YUV2RGBExtended, _DXVA_VideoProcessCaps, display.dxva_videoprocesscaps, dxva/DXVA_VideoProcessCaps, dxva/DXVA_VideoProcess_AlphaBlend, dxva/DXVA_VideoProcess_AlphaBlendExtended, dxva/DXVA_VideoProcess_None, dxva/DXVA_VideoProcess_StretchX, dxva/DXVA_VideoProcess_StretchY, dxva/DXVA_VideoProcess_SubRects, dxva/DXVA_VideoProcess_SubStreams, dxva/DXVA_VideoProcess_SubStreamsExtended, dxva/DXVA_VideoProcess_YUV2RGB, dxva/DXVA_VideoProcess_YUV2RGBExtended, dxvaref_4298738a-dc13-47b4-bb3d-84e90661542b.xml
ms.topic: enum
f1_keywords:
 - "dxva/DXVA_VideoProcessCaps"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_VideoProcessCaps
product:
- Windows
targetos: Windows
req.typenames: DXVA_VideoProcessCaps
---

# _DXVA_VideoProcessCaps enumeration


## -description


The DXVA_VideoProcessCaps enumeration identifies operations that can be performed concurrently with the requested deinterlace. 


## -enum-fields




### -field DXVA_VideoProcess_None

Indicates that the deinterlace hardware can only perform basic deinterlace operations. That is, deinterlace operations that are not combined with other operations, like-color conversion, alpha blend, stretch, subsection, or substream. 


### -field DXVA_VideoProcess_YUV2RGB

Indicates that the deinterlace hardware can convert video from the YUV color space to the RGB color space. The RGB format will have at least 8 bits of precision for each color component. If possible, a buffer copy within the VMR can be avoided. All drivers should be able to support this operation for the bob deinterlace mode. 


Not used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a> function.


### -field DXVA_VideoProcess_StretchX

Indicates that aspect ratio correction can be performed simultaneously as the video is being deinterlaced if the deinterlacer is able to stretch or shrink horizontally. The enumerator should be supported for the bob deinterlace mode.

Must use with the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a> function.



### -field DXVA_VideoProcess_StretchY

Indicates that aspect ratio adjustment is combined with a general picture resizing operation to scale the video image.

Must use with the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a> function.



### -field DXVA_VideoProcess_AlphaBlend

Indicates that the VMR will not perform a buffer copy when an alpha value is changed. It is rare that applications alter the constant alpha value associated with the video stream, so this is a low priority feature. The enumerator should be supported for the bob deinterlace mode.


Not used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a> function.



### -field DXVA_VideoProcess_SubRects

Indicates that the deinterlace hardware can deinterlace just a subrectangle region of the video image to the specified destination position. This is useful if the video image must be cropped before being processed further as the size of the output frame is reduced. 


### -field DXVA_VideoProcess_SubStreams

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.


Indicates that the deinterlace hardware can combine video substreams with the video stream.


Must use with the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a> function.


### -field DXVA_VideoProcess_SubStreamsExtended

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.


Indicates that necessary color adjustments can be made to the source video streams and substreams. These adjustments are indicated in the extended color data, as the video is deinterlaced, composited with the substreams, and written to the destination surface.

Must use with the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a> function.


### -field DXVA_VideoProcess_YUV2RGBExtended

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.


Indicates a color-space-conversion operation can be performed as the deinterlaced and composited pixels are written to the destination surface using the extended color information that is specified for the source and destination surfaces.


Must use with the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a> function.


### -field DXVA_VideoProcess_AlphaBlendExtended

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.


Indicates that an alpha-blend operation can be performed with the destination surface when the deinterlaced and composited pixels are written to the destination surface. The driver must handle background color based on the alpha value of the <b>Alpha</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_deinterlacebltex">DXVA_DeinterlaceBltEx</a> structure. When the alpha value is 1.0f, the background color is drawn opaque (without transparency). When the alpha value is 0.0f, the background should not be drawn (transparent).

Must use with the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a> function.



## -remarks



Occasionally, the aspect ratio adjustment performed by <b>DXVA_VideoProcess_AlphaBlend</b> is combined with a general picture resizing operation to scale the video image within an application-defined composition space, which is rare and not an essential feature. It is best if the scaling needed for resizing the video to fit into the application window can be done simultaneously to the scaling needed for deinterlacing, which avoids cumulative artifacts. 

Color space conversion performed by <b>DXVA_VideoProcess_YUV2RGB</b> is particularly useful within the VMR if it is combined with any (and ideally, all) of the following enumerators: <b>DXVA_VideoProcess_StretchX</b>, <b>DXVA_VideoProcess_StretchY</b>, and <b>DXVA_VideoProcess_AlphaBlend</b>. There is no requirement to convert from the RGB color space to the YUV color space.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_deinterlacecaps">DXVA_DeinterlaceCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/dxva-deinterlacebobdeviceclass-deinterlacebltex">DeinterlaceBltEx</a>
 

 

