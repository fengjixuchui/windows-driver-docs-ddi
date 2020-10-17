---
UID: NS:ks.__unnamed_struct_73
title: KSEVENT_SET (ks.h)
description: The KSEVENT_SET structure describes the events that comprise a kernel streaming event set.
old-location: stream\ksevent_set.htm
tech.root: stream
ms.assetid: 0cfe3674-2261-44f5-a916-fb786bb25fe5
ms.date: 04/23/2018
keywords: ["KSEVENT_SET structure"]
ms.keywords: "*PKSEVENT_SET, KSEVENT_SET, KSEVENT_SET structure [Streaming Media Devices], PKSEVENT_SET, PKSEVENT_SET structure pointer [Streaming Media Devices], ks-struct_f3a678ec-93b4-4b60-959a-ca750b4ac4c2.xml, ks/KSEVENT_SET, ks/PKSEVENT_SET, stream.ksevent_set"
req.header: ks.h
req.include-header: Ks.h
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
req.typenames: KSEVENT_SET, *PKSEVENT_SET
f1_keywords:
 - PKSEVENT_SET
 - ks/PKSEVENT_SET
 - KSEVENT_SET
 - ks/KSEVENT_SET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSEVENT_SET
---

# KSEVENT_SET structure


## -description

The KSEVENT_SET structure describes the events that comprise a kernel streaming event set.

## -struct-fields

### -field Set

Specifies a GUID that identifies the event set. For more information about defined event sets, see <b>Remarks</b>.

### -field EventsCount

Specifies the number of events in the event set.

### -field EventItem

Points to the beginning of the array of <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item">KSEVENT_ITEM</a> structures that describe each event in the event set. The size of the array is in the <b>EventsCount</b> member.

## -remarks

Microsoft provides several system-defined kernel streaming event set GUIDs. Minidrivers specify one of these GUIDs in the <b>Set</b> member. Kernel streaming event sets typically begin with a <i>KSEVENTSETID</i> prefix. Event set GUIDs are defined in <i>ks.h</i>, <i>ksmedia.h</i>, <i>bdamedia.h</i>, and possibly other header files.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item">KSEVENT_ITEM</a>