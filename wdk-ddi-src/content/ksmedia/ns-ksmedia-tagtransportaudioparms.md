---
UID: NS:ksmedia.tagTRANSPORTAUDIOPARMS
title: tagTRANSPORTAUDIOPARMS (ksmedia.h)
description: The TRANSPORTAUDIOPARMS structure is defined but not used.
old-location: stream\transportaudioparms.htm
tech.root: stream
ms.assetid: 591ef01a-1a89-454a-ab58-a76813a9d4c2
ms.date: 04/23/2018
keywords: ["tagTRANSPORTAUDIOPARMS structure"]
ms.keywords: "*PTRANSPORTAUDIOPARMS, PTRANSPORTAUDIOPARMS, PTRANSPORTAUDIOPARMS structure pointer [Streaming Media Devices], TRANSPORTAUDIOPARMS, TRANSPORTAUDIOPARMS structure [Streaming Media Devices], ksmedia/PTRANSPORTAUDIOPARMS, ksmedia/TRANSPORTAUDIOPARMS, stream.transportaudioparms, tagTRANSPORTAUDIOPARMS, vidcapstruct_f68139f5-186d-43da-8f9a-45d2af4f782b.xml"
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
req.typenames: TRANSPORTAUDIOPARMS, *PTRANSPORTAUDIOPARMS
f1_keywords:
 - tagTRANSPORTAUDIOPARMS
 - ksmedia/tagTRANSPORTAUDIOPARMS
 - PTRANSPORTAUDIOPARMS
 - ksmedia/PTRANSPORTAUDIOPARMS
 - TRANSPORTAUDIOPARMS
 - ksmedia/TRANSPORTAUDIOPARMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - TRANSPORTAUDIOPARMS
---

# tagTRANSPORTAUDIOPARMS structure


## -description

The TRANSPORTAUDIOPARMS structure is defined but not used.

## -struct-fields

### -field EnableOutput

Specifies the enable audio output. The default is ED_AUDIO_ALL.

### -field EnableRecord

Specifies the enable audio record. The default is zero.

### -field EnableSelsync

Specifies the selsync.

### -field Input

Specifies the audio input to use. For example, specify zero to use the first (zeroth) audio input.

### -field MonitorSource

Indicates the monitor source. The default is zero.

## -remarks

Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.

