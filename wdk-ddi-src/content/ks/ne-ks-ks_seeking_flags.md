---
UID: NE:ks.__unnamed_enum_5
title: KS_SEEKING_FLAGS (ks.h)
description: The KS_SEEKING_FLAGS enumeration lists positioning options that can be used in conjunction with the KSPROPERTY_POSITIONS structure.
old-location: stream\ks_seeking_flags.htm
tech.root: stream
ms.assetid: 8e27872e-4f38-4d0e-92bc-5e759a9db195
ms.date: 04/23/2018
keywords: ["KS_SEEKING_FLAGS enumeration"]
ms.keywords: KS_SEEKING_AbsolutePositioning, KS_SEEKING_FLAGS, KS_SEEKING_FLAGS enumeration [Streaming Media Devices], KS_SEEKING_IncrementalPositioning, KS_SEEKING_NoPositioning, KS_SEEKING_PositioningBitsMask, KS_SEEKING_RelativePositioning, KS_SEEKING_ReturnTime, KS_SEEKING_SeekToKeyFrame, ks-struct_edea1d66-55d6-4705-ae8f-b940946b87e0.xml, ks/KS_SEEKING_AbsolutePositioning, ks/KS_SEEKING_FLAGS, ks/KS_SEEKING_IncrementalPositioning, ks/KS_SEEKING_NoPositioning, ks/KS_SEEKING_PositioningBitsMask, ks/KS_SEEKING_RelativePositioning, ks/KS_SEEKING_ReturnTime, ks/KS_SEEKING_SeekToKeyFrame, stream.ks_seeking_flags
f1_keywords:
 - "ks/KS_SEEKING_FLAGS"
 - "KS_SEEKING_FLAGS"
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
- ks.h
api_name:
- KS_SEEKING_FLAGS
targetos: Windows
req.typenames: KS_SEEKING_FLAGS
---

# KS_SEEKING_FLAGS enumeration


## -description


The KS_SEEKING_FLAGS enumeration lists positioning options that can be used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_positions">KSPROPERTY_POSITIONS</a> structure.


## -enum-fields




### -field KS_SEEKING_NoPositioning


### -field KS_SEEKING_AbsolutePositioning


### -field KS_SEEKING_RelativePositioning


### -field KS_SEEKING_IncrementalPositioning


### -field KS_SEEKING_PositioningBitsMask


### -field KS_SEEKING_SeekToKeyFrame


### -field KS_SEEKING_ReturnTime


## -remarks



The minidriver sets these flag values in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_positions">KSPROPERTY_POSITIONS</a> structure that it then submits in a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-mediaseeking-positions">KSPROPERTY_MEDIASEEKING_POSITIONS</a> property request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-mediaseeking-positions">KSPROPERTY_MEDIASEEKING_POSITIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_positions">KSPROPERTY_POSITIONS</a>
 

 

