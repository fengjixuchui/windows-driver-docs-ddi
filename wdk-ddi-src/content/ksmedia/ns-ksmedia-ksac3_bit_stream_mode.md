---
UID: NS:ksmedia.__unnamed_struct_71
title: KSAC3_BIT_STREAM_MODE (ksmedia.h)
description: The KSAC3_BIT_STREAM_MODE structure specifies the bit-stream mode, which is the type of audio service that is encoded into an AC-3 stream.
old-location: audio\ksac3_bit_stream_mode.htm
tech.root: audio
ms.assetid: 1395687d-643a-40b5-9ca9-bff34c0dd6d5
ms.date: 04/30/2019
keywords: ["KSAC3_BIT_STREAM_MODE structure"]
ms.keywords: "*PKSAC3_BIT_STREAM_MODE, KSAC3_BIT_STREAM_MODE, KSAC3_BIT_STREAM_MODE structure [Audio Devices], PKSAC3_BIT_STREAM_MODE, PKSAC3_BIT_STREAM_MODE structure pointer [Audio Devices], aud-prop_b90587bf-508c-4e01-83ec-6fd925433d17.xml, audio.ksac3_bit_stream_mode, ksmedia/KSAC3_BIT_STREAM_MODE, ksmedia/PKSAC3_BIT_STREAM_MODE"
f1_keywords:
 - "ksmedia/KSAC3_BIT_STREAM_MODE"
 - "KSAC3_BIT_STREAM_MODE"
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
- KSAC3_BIT_STREAM_MODE
targetos: Windows
req.typenames: KSAC3_BIT_STREAM_MODE, *PKSAC3_BIT_STREAM_MODE
---

# KSAC3_BIT_STREAM_MODE structure


## -description


The KSAC3_BIT_STREAM_MODE structure specifies the bit-stream mode, which is the type of audio service that is encoded into an AC-3 stream.


## -struct-fields




### -field BitStreamMode

Specifies the bit-stream mode. The <b>BitStreamMode</b> member is set to a value in the range 0 to 7. Specify the value of this member as one of the following constants:

<table>
<tr>
<th>Constant name</th>
<th>Value</th>
</tr>
<tr>
<td>
KSAC3_SERVICE_MAIN_AUDIO

</td>
<td>
0

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_NO_DIALOG

</td>
<td>
1

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_VISUALLY_IMPAIRED

</td>
<td>
2

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_HEARING_IMPAIRED

</td>
<td>
3

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_DIALOG_ONLY

</td>
<td>
4

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_COMMENTARY

</td>
<td>
5

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_EMERGENCY_FLASH

</td>
<td>
6

</td>
</tr>
<tr>
<td>
KSAC3_SERVICE_VOICE_OVER

</td>
<td>
7

</td>
</tr>
</table>
 

These constants correspond to the bit-stream modes that are defined in the AC-3 specification. For more information, see the following Remarks section.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-ac3-bit-stream-mode">KSPROPERTY_AC3_BIT_STREAM_MODE</a> property.

For more information about bit stream modes, see the AC-3 specification at the <a href="https://go.microsoft.com/fwlink/p/?linkid=8730">Dolby Laboratories</a> website. The specification is titled Digital Audio Compression Standard (AC-3).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-ac3-bit-stream-mode">KSPROPERTY_AC3_BIT_STREAM_MODE</a>
 

 

