---
UID: NS:ksmedia.tagKS_DATARANGE_MPEG2_VIDEO
title: tagKS_DATARANGE_MPEG2_VIDEO (ksmedia.h)
description: The KS_DATARANGE_MPEG2_VIDEO structure describes the range of MPEG-2 video formats available for a stream.
old-location: stream\ks_datarange_mpeg2_video.htm
tech.root: stream
ms.assetid: ed29c80a-7a42-46e3-8a18-d66dfddb9659
ms.date: 04/23/2018
ms.keywords: "*PKS_DATARANGE_MPEG2_VIDEO, KS_DATARANGE_MPEG2_VIDEO, KS_DATARANGE_MPEG2_VIDEO structure [Streaming Media Devices], PKS_DATARANGE_MPEG2_VIDEO, PKS_DATARANGE_MPEG2_VIDEO structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_MPEG2_VIDEO, ksmedia/PKS_DATARANGE_MPEG2_VIDEO, stream.ks_datarange_mpeg2_video, tagKS_DATARANGE_MPEG2_VIDEO, vidcapstruct_91d79090-6aa2-4037-8436-7cb21d242e72.xml"
ms.topic: struct
f1_keywords:
 - "ksmedia/KS_DATARANGE_MPEG2_VIDEO"
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
- KS_DATARANGE_MPEG2_VIDEO
product:
- Windows
targetos: Windows
req.typenames: KS_DATARANGE_MPEG2_VIDEO, *PKS_DATARANGE_MPEG2_VIDEO
---

# tagKS_DATARANGE_MPEG2_VIDEO structure


## -description


The KS_DATARANGE_MPEG2_VIDEO structure describes the range of MPEG-2 video formats available for a stream.


## -struct-fields




### -field DataRange

Specifies the major identifier for the format.


### -field bFixedSizeSamples

Specifies that all the samples are the same size if set to <b>TRUE</b>.


### -field bTemporalCompression

Specifies whether each sample can stand independently on its own, without relying on previous or future samples.


### -field StreamDescriptionFlags

Unused and should be set to zero.


### -field MemoryAllocationFlags

Unused and should be set to zero.


### -field ConfigCaps

Specifies the configuration of the stream, including scaling, cropping, and frame and data rates.


### -field VideoInfoHeader

Specifies the details of the video stream.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-tagks_mpegvideoinfo2">KS_MPEGVIDEOINFO2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-_ks_video_stream_config_caps">KS_VIDEO_STREAM_CONFIG_CAPS</a>
 

 

