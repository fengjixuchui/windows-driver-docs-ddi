---
UID: NS:ksmedia.__unnamed_struct_146
title: KSPROPERTY_TVAUDIO_S (ksmedia.h)
description: The KSPROPERTY_TVAUDIO_S structure describes the current TV audio mode, such as stereo or mono audio and language settings.
old-location: stream\ksproperty_tvaudio_s.htm
tech.root: stream
ms.assetid: a2e26798-322a-4057-8c29-3429711e36a4
ms.date: 04/30/2019
keywords: ["KSPROPERTY_TVAUDIO_S structure"]
ms.keywords: "*PKSPROPERTY_TVAUDIO_S, KSPROPERTY_TVAUDIO_S, KSPROPERTY_TVAUDIO_S structure [Streaming Media Devices], PKSPROPERTY_TVAUDIO_S, PKSPROPERTY_TVAUDIO_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TVAUDIO_S, ksmedia/PKSPROPERTY_TVAUDIO_S, stream.ksproperty_tvaudio_s, vidcapstruct_d9dd7c2c-ed79-4efa-ae11-07e069abda5c.xml"
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
req.typenames: KSPROPERTY_TVAUDIO_S, *PKSPROPERTY_TVAUDIO_S
f1_keywords:
 - PKSPROPERTY_TVAUDIO_S
 - ksmedia/PKSPROPERTY_TVAUDIO_S
 - KSPROPERTY_TVAUDIO_S
 - ksmedia/KSPROPERTY_TVAUDIO_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_TVAUDIO_S
---

# KSPROPERTY_TVAUDIO_S structure


## -description

The KSPROPERTY_TVAUDIO_S structure describes the current TV audio mode, such as stereo or mono audio and language settings.

## -struct-fields

### -field Property

Specifies an initialized <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field Mode

Specifies the mode of the TV audio device. For Get requests, the minidriver returns the current mode of the TV audio device. For Set requests, the minidriver sets the current mode of the TV audio device to the specified value. This member can be one or more (logically ORed) of the following values:

<table>
<tr>
<th>Mode</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_MONO

</td>
<td>
Indicates that the audio is in mono.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_STEREO

</td>
<td>
Indicates that the audio is in stereo.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_LANG_A

</td>
<td>
Indicates that the audio is in the primary language.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_LANG_B

</td>
<td>
Indicates that the audio is in the second language supported by the device.

</td>
</tr>
<tr>
<td>
KS_TVAUDIO_MODE_LANG_C

</td>
<td>
Indicates that the audio is in the third language supported by the device.

</td>
</tr>
</table>

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-tvaudio-mode">KSPROPERTY_TVAUDIO_MODE</a>



<a href="/windows-hardware/drivers/stream/propsetid-vidcap-tvaudio">PROPSETID_VIDCAP_TVAUDIO</a>