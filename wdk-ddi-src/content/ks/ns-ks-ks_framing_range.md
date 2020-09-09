---
UID: NS:ks.__unnamed_struct_38
title: KS_FRAMING_RANGE (ks.h)
description: The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item.
old-location: stream\ks_framing_range.htm
tech.root: stream
ms.assetid: 3263b290-2966-4e19-9828-b91e7b2efa55
ms.date: 04/23/2018
keywords: ["KS_FRAMING_RANGE structure"]
ms.keywords: "*PKS_FRAMING_RANGE, KS_FRAMING_RANGE, KS_FRAMING_RANGE structure [Streaming Media Devices], PKS_FRAMING_RANGE, PKS_FRAMING_RANGE structure pointer [Streaming Media Devices], ks-struct_a489de91-e530-4185-9344-0ab4fe426cc8.xml, ks/KS_FRAMING_RANGE, ks/PKS_FRAMING_RANGE, stream.ks_framing_range"
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
req.typenames: KS_FRAMING_RANGE, *PKS_FRAMING_RANGE
f1_keywords:
 - PKS_FRAMING_RANGE
 - ks/PKS_FRAMING_RANGE
 - KS_FRAMING_RANGE
 - ks/KS_FRAMING_RANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KS_FRAMING_RANGE
---

# KS_FRAMING_RANGE structure


## -description

The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item.

## -struct-fields

### -field MinFrameSize

Specifies a minimum frame size of type ULONG.

### -field MaxFrameSize

Specifies a maximum frame size of type ULONG.

### -field Stepping

Specifies the step value that should be used to create legal values within the range defined in <b>MinFrameSize</b> and <b>MaxFrameSize</b>.

## -remarks

When specifying the <b>Stepping</b> member, ensure that the value does not exceed the difference between the <b>MinFrameSize</b> and <b>MaxFrameSize</b> members. Otherwise, unpredictable behavior may result.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_item">KS_FRAMING_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_range_weighted">KS_FRAMING_RANGE_WEIGHTED</a>

