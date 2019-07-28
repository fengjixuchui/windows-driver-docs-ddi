---
UID: NE:ks.__unnamed_enum_24
title: KSPROPERTY_STREAM (ks.h)
description: 
old-location: stream\ksproperty_stream.htm
tech.root: stream
ms.assetid: 1A7C7181-00AF-4AAB-822F-017F11DB9409
ms.date: 04/23/2018
ms.keywords: KSPROPERTY_STREAM, KSPROPERTY_STREAM enumeration [Streaming Media Devices], KSPROPERTY_STREAM_ALLOCATOR, KSPROPERTY_STREAM_DEGRADATION, KSPROPERTY_STREAM_FRAMETIME, KSPROPERTY_STREAM_MASTERCLOCK, KSPROPERTY_STREAM_PIPE_ID, KSPROPERTY_STREAM_PRESENTATIONEXTENT, KSPROPERTY_STREAM_PRESENTATIONTIME, KSPROPERTY_STREAM_QUALITY, KSPROPERTY_STREAM_RATE, KSPROPERTY_STREAM_RATECAPABILITY, KSPROPERTY_STREAM_TIMEFORMAT, ks/KSPROPERTY_STREAM, ks/KSPROPERTY_STREAM_ALLOCATOR, ks/KSPROPERTY_STREAM_DEGRADATION, ks/KSPROPERTY_STREAM_FRAMETIME, ks/KSPROPERTY_STREAM_MASTERCLOCK, ks/KSPROPERTY_STREAM_PIPE_ID, ks/KSPROPERTY_STREAM_PRESENTATIONEXTENT, ks/KSPROPERTY_STREAM_PRESENTATIONTIME, ks/KSPROPERTY_STREAM_QUALITY, ks/KSPROPERTY_STREAM_RATE, ks/KSPROPERTY_STREAM_RATECAPABILITY, ks/KSPROPERTY_STREAM_TIMEFORMAT, stream.ksproperty_stream
ms.topic: enum
f1_keywords:
 - "ks/KSPROPERTY_STREAM"
req.header: ks.h
req.include-header: 
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
- Ks.h
api_name:
- KSPROPERTY_STREAM
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_STREAM
---

# KSPROPERTY_STREAM enumeration


## -description





## -enum-fields




### -field KSPROPERTY_STREAM_ALLOCATOR

Specify if the pin allocates stream buffers or can provide an allocator.


### -field KSPROPERTY_STREAM_QUALITY

Specify if the pin generates Quality Management complaints.


### -field KSPROPERTY_STREAM_DEGRADATION

Specify if the pin allows degradation strategies.


### -field KSPROPERTY_STREAM_MASTERCLOCK

Specify if the pin uses or produces a master clock that can be used for synchronization.


### -field KSPROPERTY_STREAM_TIMEFORMAT

Specify to retrieve the time format used on a particular pin connection.


### -field KSPROPERTY_STREAM_PRESENTATIONTIME

Specify to retrieve and set the current presentation time of a filter pin.


### -field KSPROPERTY_STREAM_PRESENTATIONEXTENT

Specify to query the stream extent.


### -field KSPROPERTY_STREAM_FRAMETIME

Specify to determine the duration of the next frame based on the particular media stream, and use that information to step-frame a sequence.


### -field KSPROPERTY_STREAM_RATECAPABILITY

Specify to allow a graph manager to query all connection points involved in the flow of a particular stream (obtained through KSPROPERTY_PIN_DATAROUTING) for their capability in adjusting a requested rate to the nominal rate.


### -field KSPROPERTY_STREAM_RATE

Specify in conjunction with KSPROPERTY_STREAM_RATECAPABILITY and use this to set the rate of a segment after querying the capability of the pin.


### -field KSPROPERTY_STREAM_PIPE_ID

Used internally for communication between the KSProxy system driver and AVStream.

