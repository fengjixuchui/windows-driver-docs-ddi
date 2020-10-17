---
UID: NE:ksmedia.__unnamed_enum_54
title: KS_MPEG2Profile (ksmedia.h)
description: The KS_MPEG2Profile enumeration describes MPEG-2 profiles.
old-location: stream\ks_mpeg2profile.htm
tech.root: stream
ms.assetid: 1846e6b7-5b98-4850-86d6-ef6a29ce050b
ms.date: 04/30/2019
keywords: ["KS_MPEG2Profile enumeration"]
ms.keywords: KS_MPEG2Profile, KS_MPEG2Profile enumeration [Streaming Media Devices], KS_MPEG2Profile_High, KS_MPEG2Profile_Main, KS_MPEG2Profile_SNRScalable, KS_MPEG2Profile_Simple, KS_MPEG2Profile_SpatiallyScalable, ksmedia/KS_MPEG2Profile, ksmedia/KS_MPEG2Profile_High, ksmedia/KS_MPEG2Profile_Main, ksmedia/KS_MPEG2Profile_SNRScalable, ksmedia/KS_MPEG2Profile_Simple, ksmedia/KS_MPEG2Profile_SpatiallyScalable, stream.ks_mpeg2profile, vidcapstruct_25932d29-3acc-415e-a13f-f02298c12c1d.xml
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
req.typenames: KS_MPEG2Profile
f1_keywords:
 - KS_MPEG2Profile
 - ksmedia/KS_MPEG2Profile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_MPEG2Profile
---

# KS_MPEG2Profile enumeration


## -description

The KS_MPEG2Profile enumeration describes MPEG-2 profiles.

## -enum-fields

### -field KS_MPEG2Profile_Simple

Specifies the simple MPEG-2 profile, generally intended for software applications and some cable television.

### -field KS_MPEG2Profile_Main

Specifies the main MPEG-2 profile, generally intended for cable or satellite television.

### -field KS_MPEG2Profile_SNRScalable

Similar to <b>KS_MPEG2Profile_Main</b>, with scalable signal-to-noise.

### -field KS_MPEG2Profile_SpatiallyScalable

Similar to <b>KS_MPEG2Profile_Main</b>, with spatial scalability.

### -field KS_MPEG2Profile_High

Similar to <b>KS_MPEG2Profile_Main</b>, with spatial scalability, scalable signal-to-noise, and 4:2:2 macroblocks.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagks_mpegvideoinfo2">KS_MPEGVIDEOINFO2</a>