---
UID: NS:d3dumddi._DXVADDI_VIDEODESC
title: _DXVADDI_VIDEODESC (d3dumddi.h)
description: The DXVADDI_VIDEODESC structure describes a video stream.
old-location: display\dxvaddi_videodesc.htm
tech.root: display
ms.assetid: 19121888-ad5c-4596-a7ec-a95fbffda685
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_7e8c3d70-50a3-48f7-bc5e-4280a599e43d.xml, DXVADDI_VIDEODESC, DXVADDI_VIDEODESC structure [Display Devices], _DXVADDI_VIDEODESC, d3dumddi/DXVADDI_VIDEODESC, display.dxvaddi_videodesc
ms.topic: struct
f1_keywords:
 - "d3dumddi/DXVADDI_VIDEODESC"
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
- DXVADDI_VIDEODESC
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_VIDEODESC
---

# _DXVADDI_VIDEODESC structure


## -description


The DXVADDI_VIDEODESC structure describes a video stream.


## -struct-fields




### -field SampleWidth

[in] The width of the video sample, in pixels.


### -field SampleHeight

[in] The height of the video sample, in pixels.


### -field SampleFormat

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a> structure that describes the extended format of the video sample.


### -field Format

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a> structure that describes the extended format of the video sample.


### -field InputSampleFreq

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_frequency">DXVADDI_FREQUENCY</a> structure that defines the frequency of incoming video.


### -field OutputFrameFreq

[in] A DXVADDI_FREQUENCY structure that defines the frame rate of output video.


### -field UABProtectionLevel

[in] A UINT value that specifies the level of data protection that is required when the user accessible bus is present.


### -field Reserved

[in] Reserved. Do not use this member.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_frequency">DXVADDI_FREQUENCY</a>
 

 

