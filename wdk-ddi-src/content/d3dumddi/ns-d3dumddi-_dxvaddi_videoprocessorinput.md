---
UID: NS:d3dumddi._DXVADDI_VIDEOPROCESSORINPUT
title: _DXVADDI_VIDEOPROCESSORINPUT (d3dumddi.h)
description: The DXVADDI_VIDEOPROCESSORINPUT structure describes a video stream that is processed by a video processing device type.
old-location: display\dxvaddi_videoprocessorinput.htm
tech.root: display
ms.assetid: 539d32a5-4566-4b8e-b9de-da8d5be3c2f2
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_87cc7918-2fb5-4b73-a62c-ab9a3817c154.xml, DXVADDI_VIDEOPROCESSORINPUT, DXVADDI_VIDEOPROCESSORINPUT structure [Display Devices], _DXVADDI_VIDEOPROCESSORINPUT, d3dumddi/DXVADDI_VIDEOPROCESSORINPUT, display.dxvaddi_videoprocessorinput
ms.topic: struct
f1_keywords:
 - "d3dumddi/DXVADDI_VIDEOPROCESSORINPUT"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- DXVADDI_VIDEOPROCESSORINPUT
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOPROCESSORINPUT
---

# _DXVADDI_VIDEOPROCESSORINPUT structure


## -description


The DXVADDI_VIDEOPROCESSORINPUT structure describes a video stream that is processed by a video processing device type.


## -struct-fields




### -field pVideoProcGuid

[in] A pointer to a GUID that represents the video processing device type. 


### -field VideoDesc

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a> structure that describes the video stream. 


### -field RenderTargetFormat

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.


## -remarks



When the D3DDDICAPS_GETVIDEOPROCESSORRTFORMATCOUNT, D3DDDICAPS_GETVIDEOPROCESSORRTFORMATS, D3DDDICAPS_GETVIDEOPROCESSORRTSUBSTREAMFORMATCOUNT, or D3DDDICAPS_GETVIDEOPROCESSORRTSUBSTREAMFORMATS <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>-type value is sent in a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function, the driver ignores the <b>RenderTargetFormat</b> member of DXVADDI_VIDEOPROCESSORINPUT.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videoprocessorcaps">DXVADDI_VIDEOPROCESSORCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
 

 

