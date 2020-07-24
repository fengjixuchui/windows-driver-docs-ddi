---
UID: NS:ksmedia.__unnamed_struct_135
title: MEDIUM_INFO (ksmedia.h)
description: The MEDIUM_INFO structure describes the media loaded into an external device.
old-location: stream\medium_info.htm
tech.root: stream
ms.assetid: 1dd7415d-bfbc-4dea-bac9-bc5b8531a47f
ms.date: 04/30/2019
keywords: ["MEDIUM_INFO structure"]
ms.keywords: "*PMEDIUM_INFO, MEDIUM_INFO, MEDIUM_INFO structure [Streaming Media Devices], PMEDIUM_INFO, PMEDIUM_INFO structure pointer [Streaming Media Devices], ksmedia/MEDIUM_INFO, ksmedia/PMEDIUM_INFO, stream.medium_info, vidcapstruct_f83c29e1-51a8-4784-a785-4e5dc9956634.xml"
f1_keywords:
 - "ksmedia/MEDIUM_INFO"
 - "MEDIUM_INFO"
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
- MEDIUM_INFO
targetos: Windows
req.typenames: MEDIUM_INFO, *PMEDIUM_INFO
---

# MEDIUM_INFO structure


## -description


The MEDIUM_INFO structure describes the media loaded into an external device.


## -struct-fields




### -field MediaPresent

Specifies if media is present in the external device. <b>TRUE</b> if media is loaded, <b>FALSE</b> otherwise.


### -field MediaType

Indicates the type of the media loaded in an external device.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_MEDIA_DVC

</td>
<td>
Digital video cassette. For example MiniDV

</td>
</tr>
<tr>
<td>
ED_MEDIA_VHS

</td>
<td>
VHS cassette

</td>
</tr>
<tr>
<td>
ED_MEDIA_HI8

</td>
<td>
Hi-8 cassette

</td>
</tr>
</table>
 


### -field RecordInhibit

Specifies if recording is inhibited on the media. <b>TRUE</b> if recording onto the media is inhibited, <b>FALSE</b> otherwise.


## -remarks



Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.



