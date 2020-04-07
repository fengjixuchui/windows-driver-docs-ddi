---
UID: NS:ks.__unnamed_struct_32
title: KSATTRIBUTE_LIST (ks.h)
description: The KSATTRIBUTE_LIST structure contains an attribute defined in a KSATTRIBUTE structure.
old-location: stream\ksattribute_list.htm
tech.root: stream
ms.assetid: 4E533E77-9288-45DF-8C93-2A6EACADF9FF
ms.date: 04/23/2018
keywords: ["KSATTRIBUTE_LIST structure"]
ms.keywords: "*PKSATTRIBUTE_LIST, KSATTRIBUTE_LIST, KSATTRIBUTE_LIST structure [Streaming Media Devices], PKSATTRIBUTE_LIST, PKSATTRIBUTE_LIST structure pointer [Streaming Media Devices], ks/KSATTRIBUTE_LIST, ks/PKSATTRIBUTE_LIST, stream.ksattribute_list"
f1_keywords:
 - "ks/KSATTRIBUTE_LIST"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ks.h
api_name:
- KSATTRIBUTE_LIST
product:
- Windows
targetos: Windows
req.typenames: KSATTRIBUTE_LIST, *PKSATTRIBUTE_LIST
---

# KSATTRIBUTE_LIST structure


## -description


The KSATTRIBUTE_LIST structure contains an attribute defined in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksattribute">KSATTRIBUTE</a> structure.

This structure is used to by mode aware drivers with  <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>. The KSATTRIBUTE_LIST has a single element, which is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksattribute">KSATTRIBUTE</a>. The Attribute member of the <b>KSATTRIBUTE</b> structure is set to KSATTRIBUTEID_AUDIOSIGNALPROCESSING_MODE.


## -struct-fields




### -field Count

Specifies the number of attributes in the list.


### -field Attributes

  A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksattribute">KSATTRIBUTE</a> structure who's Attribute member is set to <i>KSATTRIBUTEID_AUDIOSIGNALPROCESSING_MODE</i>. For more information,  see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-signal-processing-modes">Audio Signal Processing Modes</a>.

