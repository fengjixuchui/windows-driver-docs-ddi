---
UID: NE:ks.__unnamed_enum_1
title: KSSTATE (ks.h)
description: The KSSTATE enumeration lists possible states of a kernel streaming object.
old-location: stream\ksstate.htm
tech.root: stream
ms.assetid: 6f5a3c65-9d6c-4d5f-af99-71aba16eb254
ms.date: 04/23/2018
keywords: ["KSSTATE enumeration"]
ms.keywords: "*PKSSTATE, KSSTATE, KSSTATE enumeration [Streaming Media Devices], KSSTATE_ACQUIRE, KSSTATE_PAUSE, KSSTATE_RUN, KSSTATE_STOP, PKSSTATE, PKSSTATE enumeration pointer [Streaming Media Devices], ks-struct_a5862576-6737-471e-8e31-1bc98fb4b4f9.xml, ks/KSSTATE, ks/KSSTATE_ACQUIRE, ks/KSSTATE_PAUSE, ks/KSSTATE_RUN, ks/KSSTATE_STOP, ks/PKSSTATE, stream.ksstate"
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
req.typenames: KSSTATE, *PKSSTATE
f1_keywords:
 - PKSSTATE
 - ks/PKSSTATE
 - KSSTATE
 - ks/KSSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSSTATE
---

# KSSTATE enumeration


## -description

The KSSTATE enumeration lists possible states of a kernel streaming object.

## -enum-fields

### -field KSSTATE_STOP

Indicates that the object is in minimum resource consumption mode.

### -field KSSTATE_ACQUIRE

Indicates that the object is acquiring resources.

### -field KSSTATE_PAUSE

Indicates that the object is preparing to make instant transition to Run state.

### -field KSSTATE_RUN

Indicates that the object is actively streaming.

