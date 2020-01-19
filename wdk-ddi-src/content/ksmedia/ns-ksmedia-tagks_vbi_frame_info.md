---
UID: NS:ksmedia.tagKS_VBI_FRAME_INFO
title: tagKS_VBI_FRAME_INFO (ksmedia.h)
description: The KS_VBI_FRAME_INFO structure extends the KSSTREAM_HEADER structure for vertical blanking interval (VBI) streams.
old-location: stream\ks_vbi_frame_info.htm
tech.root: stream
ms.assetid: ae6ba1c3-0729-41bd-9fd5-62969bf4b70c
ms.date: 04/23/2018
ms.keywords: "*PKS_VBI_FRAME_INFO, KS_VBI_FRAME_INFO, KS_VBI_FRAME_INFO structure [Streaming Media Devices], PKS_VBI_FRAME_INFO, PKS_VBI_FRAME_INFO structure pointer [Streaming Media Devices], ksmedia/KS_VBI_FRAME_INFO, ksmedia/PKS_VBI_FRAME_INFO, stream.ks_vbi_frame_info, tagKS_VBI_FRAME_INFO, vidcapstruct_4056b888-5d3a-422b-afdb-bc686b853e8b.xml"
ms.topic: struct
f1_keywords:
 - "ksmedia/KS_VBI_FRAME_INFO"
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
- KS_VBI_FRAME_INFO
product:
- Windows
targetos: Windows
req.typenames: KS_VBI_FRAME_INFO, *PKS_VBI_FRAME_INFO
---

# tagKS_VBI_FRAME_INFO structure


## -description


The KS_VBI_FRAME_INFO structure extends the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a> structure for vertical blanking interval (VBI) streams.


## -struct-fields




### -field ExtendedHeaderSize

Specifies the size of this structure.


### -field dwFrameFlags

Specifies flags indicating additional information about the frame captured. During capture, the minidriver sets this member to one of the following values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_VBI_FLAG_FIELD1

</td>
<td>
Indicates the first field of a two-field sequence

</td>
</tr>
<tr>
<td>
KS_VBI_FLAG_FIELD2

</td>
<td>
Indicates the second field of a two-field sequence

</td>
</tr>
<tr>
<td>
KS_VBI_FLAG_MV_PRESENT

</td>
<td>
Indicates Macrovision protection scheme

</td>
</tr>
<tr>
<td>
KS_VBI_FLAG_MV_HARDWARE

</td>
<td>
Indicates Macrovision hardware support

</td>
</tr>
<tr>
<td>
KS_VBI_FLAG_MV_DETECTED

</td>
<td>
Indicates Macrovision detected

</td>
</tr>
<tr>
<td>
KS_VBI_FLAG_TVTUNER_CHANGE

</td>
<td>
Indicates that the <b>TvTunerChangeInfo</b> member structure contains valid data

</td>
</tr>
<tr>
<td>
KS_VBI_FLAG_VBIINFOHEADER_CHANGE

</td>
<td>
Indicates that the <b>VBIInfoHeader</b> member structure contains valid data

</td>
</tr>
</table>
 


### -field PictureNumber

Specifies a count representing the current picture number. Initialize or update this value on transition into KSSTATE_ACQUIRE.


### -field DropCount

Specifies the number of pictures that were not captured. When capturing video, the minidriver sets this member. This counter should be incremented whenever a frame should have been captured but was not; this condition usually arises when no buffers were available during capture. Initialize or update this value on transition into KSSTATE_ACQUIRE.


### -field dwSamplingFrequency

Specifies the sampling frequency in hertz (Hz).


### -field TvTunerChangeInfo

Specifies information about the current VBI data source, including country/region code, analog video standard, and channel. This member is only valid if <b>dwFrameFlags</b> specifies the KS_VBI_FLAG_TVTUNER_CHANGE flag. 


### -field VBIInfoHeader

Specifies information about the current VBI data source, including start line, end line, sampling frequency, and video standard. This member is only valid if <b>dwFrameFlags</b> specifies the KS_VBI_FLAG_VBIINFOHEADER_CHANGE flag.


## -remarks



The KS_VBI_FRAME_INFO structure provides a way to return information about a captured frame, as well as providing tuning information to VBI decoders.

The <b>PictureNumber</b> member count represents the count of the current picture based on the format used to open the stream. This count is calculated in one of two ways, depending on the device:

<ol>
<li>
Measure the time since the stream was started and divide by the frame duration. This method is appropriate for devices that do not provide their own clock. For example: <i>PictureNumber = (CurrentStreamTime − StartStreamTime) / FrameDuration</i>

</li>
<li>
Add together the count of frames captured and the count of frames dropped. This method is appropriate for devices that provide their own clock. For example: <i>PictureNumber = FramesCaptured + FramesDropped</i>

</li>
</ol>
When calculating the <b>PictureNumber</b> and <b>DropCount</b>, it is important to use the frame duration specified when the stream was opened, which may not necessarily match the rate at which the device is actually producing images. For example, a USB camera may only produce images at 7.5 fps, but a client could open the stream at 8 fps. In this case, all calculations should use the 8 fps number. For more information about updating <b>PictureNumber</b> and <b>DropCount</b> see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/capturing-video">Capturing Video</a>.

The <b>dwSamplingFrequency</b> member is not used by Microsoft VBI codecs, but may be used by other WDM codecs. It must be the same as the <b>VBIInfoHeader</b>.<i>SamplingFrequency</i> member. A minidriver indicates a change in sampling frequency by setting the KS_VBI_FLAG_VBIINFOHEADER_CHANGE bit in the <b>dwFrameFlags</b> member, and filling in all members, including <b>dwSamplingFrequency</b>, in the <b>VBIInfoHeader</b> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_tvtuner_change_info">KS_TVTUNER_CHANGE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_vbiinfoheader">KS_VBIINFOHEADER</a>
 

 

