---
UID: NS:ksmedia.__unnamed_struct_44
title: KSAUDIO_MIXLEVEL (ksmedia.h)
description: The KSAUDIO_MIXLEVEL structure specifies the mixing level of an input-output path in a supermixer node (KSNODETYPE_SUPERMIX).
old-location: audio\ksaudio_mixlevel.htm
tech.root: audio
ms.assetid: b685f2f5-3491-471d-b1da-07a7e56bda62
ms.date: 07/08/2019
keywords: ["KSAUDIO_MIXLEVEL structure"]
ms.keywords: "*PKSAUDIO_MIXLEVEL, KSAUDIO_MIXLEVEL, KSAUDIO_MIXLEVEL structure [Audio Devices], PKSAUDIO_MIXLEVEL, PKSAUDIO_MIXLEVEL structure pointer [Audio Devices], aud-prop_d80f29a4-4872-49cc-b1af-94b69be9c229.xml, audio.ksaudio_mixlevel, ksmedia/KSAUDIO_MIXLEVEL, ksmedia/PKSAUDIO_MIXLEVEL"
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
targetos: Windows
req.typenames: KSAUDIO_MIXLEVEL, *PKSAUDIO_MIXLEVEL
f1_keywords:
 - PKSAUDIO_MIXLEVEL
 - ksmedia/PKSAUDIO_MIXLEVEL
 - KSAUDIO_MIXLEVEL
 - ksmedia/KSAUDIO_MIXLEVEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSAUDIO_MIXLEVEL
---

# KSAUDIO_MIXLEVEL structure


## -description

The KSAUDIO_MIXLEVEL structure specifies the mixing level of an input-output path in a supermixer node (<a href="/windows-hardware/drivers/audio/ksnodetype-supermix">KSNODETYPE_SUPERMIX</a>).

## -struct-fields

### -field Mute

Specifies whether the input channel is muted (not mixed) as it flows into the output channel. A value of <b>TRUE</b> indicates that the channel is muted. A value of <b>FALSE</b> indicates that the channel's mix level is specified by the <b>Level</b> member.

### -field Level

Specifies the mix level that is applied to the input channel as it flows into the output channel. For more information, see the following Remarks section.

## -remarks

A KSAUDIO_MIXLEVEL structure specifies the volume level of a particular data path from one input channel of a supermixer node to an output channel of the same node. An array of these structures is needed to specify the volume levels for all the input-output paths through a supermixer node.

To specify the mixing levels of all paths through a supermixer node with <i>m</i> input channels and <i>n</i> output channels requires a mix-level table consisting of an <i>m</i> x <i>n</i> array of KSAUDIO_MIXLEVEL structures. This table is used to set or get the data value for the <a href="/windows-hardware/drivers/audio/ksproperty-audio-mix-level-table">KSPROPERTY_AUDIO_MIX_LEVEL_TABLE</a> property.

The mix-level value in the <b>Level</b> member uses the following scale:

-2147483648 is -Infinity decibels (attenuation), 

 -2147483647 is -32767.99998474 decibels (attenuation), and

+2147483647 is +32767.99998474 decibels (gain).

A decibel range represented by integer values -2147483648 to +2147483647, where 

This scale has a resolution of 1/65536 decibel.

## -see-also

<a href="/windows-hardware/drivers/audio/ksnodetype-supermix">KSNODETYPE_SUPERMIX</a>



<a href="/windows-hardware/drivers/audio/ksproperty-audio-mix-level-caps">KSPROPERTY_AUDIO_MIX_LEVEL_CAPS</a>



<a href="/windows-hardware/drivers/audio/ksproperty-audio-mix-level-table">KSPROPERTY_AUDIO_MIX_LEVEL_TABLE</a>