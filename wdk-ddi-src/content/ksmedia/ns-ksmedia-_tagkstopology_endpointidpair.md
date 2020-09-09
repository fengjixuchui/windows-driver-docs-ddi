---
UID: NS:ksmedia._tagKSTOPOLOGY_ENDPOINTIDPAIR
title: _tagKSTOPOLOGY_ENDPOINTIDPAIR (ksmedia.h)
description: The KSTOPOLOGY_ENDPOINTIDPAIR structure specifies the render and capture endpoint IDs to use for the KSPROPERTY_TELEPHONY_ENDPOINTIDPAIR property.
old-location: audio\kstopology_endpointidpair.htm
tech.root: audio
ms.assetid: 556B56A6-1EF4-406B-A9FB-901C0CF24BC0
ms.date: 05/08/2018
keywords: ["tagKSTOPOLOGY_ENDPOINTIDPAIR structure"]
ms.keywords: "*PKSTOPOLOGY_ENDPOINTIDPAIR, KSTOPOLOGY_ENDPOINTIDPAIR, KSTOPOLOGY_ENDPOINTIDPAIR structure [Audio Devices], PKSTOPOLOGY_ENDPOINTIDPAIR, PKSTOPOLOGY_ENDPOINTIDPAIR structure pointer [Audio Devices], _tagKSTOPOLOGY_ENDPOINTIDPAIR, audio.kstopology_endpointidpair, ksmedia/KSTOPOLOGY_ENDPOINTIDPAIR, ksmedia/PKSTOPOLOGY_ENDPOINTIDPAIR"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
req.target-min-winversvr: Windows Server 2016
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
req.typenames: KSTOPOLOGY_ENDPOINTIDPAIR, *PKSTOPOLOGY_ENDPOINTIDPAIR
f1_keywords:
 - _tagKSTOPOLOGY_ENDPOINTIDPAIR
 - ksmedia/_tagKSTOPOLOGY_ENDPOINTIDPAIR
 - PKSTOPOLOGY_ENDPOINTIDPAIR
 - ksmedia/PKSTOPOLOGY_ENDPOINTIDPAIR
 - KSTOPOLOGY_ENDPOINTIDPAIR
 - ksmedia/KSTOPOLOGY_ENDPOINTIDPAIR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSTOPOLOGY_ENDPOINTIDPAIR
---

# _tagKSTOPOLOGY_ENDPOINTIDPAIR structure


## -description

The <b>KSTOPOLOGY_ENDPOINTIDPAIR</b> structure specifies the render and capture endpoint IDs to use for the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-telephony-endpointidpair">KSPROPERTY_TELEPHONY_ENDPOINTIDPAIR</a> property.

## -struct-fields

### -field RenderEndpoint

Specifies the render endpoint ID.

### -field CaptureEndpoint

Specifies the capture endpoint ID.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_tagkstopology_endpointid">KSTOPOLOGY_ENDPOINTID</a>

