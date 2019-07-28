---
UID: NS:ksmedia.__unnamed_struct_147
title: KSPROPERTY_VIDEOCOMPRESSION_S (ksmedia.h)
description: The KSPROPERTY_VIDEOCOMPRESSION_S structure describes a single KSPROPERTY_VIDEOCOMPRESSION_Xxx property of a specified stream.
old-location: stream\ksproperty_videocompression_s.htm
tech.root: stream
ms.assetid: 0fc80a67-de81-4cdf-8c38-bbf78c62d017
ms.date: 04/30/2019
ms.keywords: "*PKSPROPERTY_VIDEOCOMPRESSION_S, KSPROPERTY_VIDEOCOMPRESSION_S, KSPROPERTY_VIDEOCOMPRESSION_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOCOMPRESSION_S, PKSPROPERTY_VIDEOCOMPRESSION_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOCOMPRESSION_S, ksmedia/PKSPROPERTY_VIDEOCOMPRESSION_S, stream.ksproperty_videocompression_s, vidcapstruct_c3680216-5804-48a0-beac-f1b8c24b9eb5.xml"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSPROPERTY_VIDEOCOMPRESSION_S"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
- ksmedia.h
api_name:
- KSPROPERTY_VIDEOCOMPRESSION_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOCOMPRESSION_S, *PKSPROPERTY_VIDEOCOMPRESSION_S
---

# KSPROPERTY_VIDEOCOMPRESSION_S structure


## -description


The KSPROPERTY_VIDEOCOMPRESSION_S structure describes a single KSPROPERTY_VIDEOCOMPRESSION_Xxx property of a specified stream. 


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field StreamIndex

Contains the zero-based index of the stream.


### -field Value

Specifies the value of a request. For Set requests, the minidriver must set the property specified in <b>Property</b> to this value. For Get requests, the minidriver must return the value of the property specified in <b>Property</b>.


## -remarks



All KSPROPERTY_VIDEOCOMPRESSION properties that use this structure are read/write.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-videocompression-keyframe-rate">KSPROPERTY_VIDEOCOMPRESSION_KEYFRAME_RATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-videocompression-override-frame-size">KSPROPERTY_VIDEOCOMPRESSION_OVERRIDE_FRAME_SIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-videocompression-override-keyframe">KSPROPERTY_VIDEOCOMPRESSION_OVERRIDE_KEYFRAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-videocompression-pframes-per-keyframe">KSPROPERTY_VIDEOCOMPRESSION_PFRAMES_PER_KEYFRAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-videocompression-quality">KSPROPERTY_VIDEOCOMPRESSION_QUALITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-videocompression-windowsize">KSPROPERTY_VIDEOCOMPRESSION_WINDOWSIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-vidcap-videocompression">PROPSETID_VIDCAP_VIDEOCOMPRESSION</a>
 

 

