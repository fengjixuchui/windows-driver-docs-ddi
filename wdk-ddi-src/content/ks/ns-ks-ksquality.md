---
UID: NS:ks.__unnamed_struct_62
title: KSQUALITY (ks.h)
description: The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers.
old-location: stream\ksquality.htm
tech.root: stream
ms.assetid: 36caaea9-2354-4ed8-9649-5eb102def8d5
ms.date: 04/23/2018
keywords: ["KSQUALITY structure"]
ms.keywords: "*PKSQUALITY, KSQUALITY, KSQUALITY structure [Streaming Media Devices], PKSQUALITY, PKSQUALITY structure pointer [Streaming Media Devices], ks-struct_a2b63e1c-e5b4-437d-a5ba-0746f8388eef.xml, ks/KSQUALITY, ks/PKSQUALITY, stream.ksquality"
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
req.typenames: KSQUALITY, *PKSQUALITY
f1_keywords:
 - PKSQUALITY
 - ks/PKSQUALITY
 - KSQUALITY
 - ks/KSQUALITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSQUALITY
---

# KSQUALITY structure


## -description

The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers.

## -struct-fields

### -field Context

Specifies a context parameter that was originally passed to the connection.

### -field Proportion

Indicates the percentage of frames currently being received that are actually being used. This is expressed in units of one-tenth of a percent, where 1000 is optimal.

### -field DeltaTime

Indicates the delta in native units (as indicated by the Interface) from optimal time at which the frames are being delivered, where a positive number means too late, and a negative number means too early. Zero indicates a correct delta.

