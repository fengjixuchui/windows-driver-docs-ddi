---
UID: NE:ksmedia.__unnamed_enum_57
title: CAPTURE_MEMORY_ALLOCATION_FLAGS (ksmedia.h)
description: The CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration defines types of memory surfaces to which AVStream minidrivers can capture audio and video data.
old-location: stream\capture_memory_allocation_flags.htm
tech.root: stream
ms.assetid: 3b96301a-28a5-494b-bd12-8d3d4516730e
ms.date: 04/30/2019
keywords: ["CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration"]
ms.keywords: "*PCAPTURE_MEMORY_ALLOCATION_FLAGS, CAPTURE_MEMORY_ALLOCATION_FLAGS, CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration [Streaming Media Devices], KS_CAPTURE_ALLOC_INVALID, KS_CAPTURE_ALLOC_SYSTEM, KS_CAPTURE_ALLOC_SYSTEM_AGP, KS_CAPTURE_ALLOC_VRAM, KS_CAPTURE_ALLOC_VRAM_MAPPED, PCAPTURE_MEMORY_ALLOCATION_FLAGS, PCAPTURE_MEMORY_ALLOCATION_FLAGS enumeration pointer [Streaming Media Devices], avstruct_2c1411b2-f4a6-44f9-ba68-63f2f5654105.xml, ksmedia/CAPTURE_MEMORY_ALLOCATION_FLAGS, ksmedia/KS_CAPTURE_ALLOC_INVALID, ksmedia/KS_CAPTURE_ALLOC_SYSTEM, ksmedia/KS_CAPTURE_ALLOC_SYSTEM_AGP, ksmedia/KS_CAPTURE_ALLOC_VRAM, ksmedia/KS_CAPTURE_ALLOC_VRAM_MAPPED, ksmedia/PCAPTURE_MEMORY_ALLOCATION_FLAGS, stream.capture_memory_allocation_flags"
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
req.typenames: CAPTURE_MEMORY_ALLOCATION_FLAGS, *PCAPTURE_MEMORY_ALLOCATION_FLAGS
f1_keywords:
 - PCAPTURE_MEMORY_ALLOCATION_FLAGS
 - ksmedia/PCAPTURE_MEMORY_ALLOCATION_FLAGS
 - CAPTURE_MEMORY_ALLOCATION_FLAGS
 - ksmedia/CAPTURE_MEMORY_ALLOCATION_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - CAPTURE_MEMORY_ALLOCATION_FLAGS
---

# CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration


## -description

The CAPTURE_MEMORY_ALLOCATION_FLAGS enumeration defines types of memory surfaces to which AVStream minidrivers can capture audio and video data. The <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-preferred-capture-surface">KSPROPERTY_PREFERRED_CAPTURE_SURFACE</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-current-capture-surface">KSPROPERTY_CURRENT_CAPTURE_SURFACE</a> requests use this type to specify property values.

## -enum-fields

### -field KS_CAPTURE_ALLOC_INVALID

Invalid memory surface.

### -field KS_CAPTURE_ALLOC_SYSTEM

Not currently supported.

### -field KS_CAPTURE_ALLOC_VRAM

Identifies a surface in display memory.

### -field KS_CAPTURE_ALLOC_SYSTEM_AGP

Identifies a surface in system memory that is tagged as AGP accessible.

### -field KS_CAPTURE_ALLOC_VRAM_MAPPED

Not currently supported.

### -field KS_CAPTURE_ALLOC_SECURE_BUFFER

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-current-capture-surface">KSPROPERTY_CURRENT_CAPTURE_SURFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-preferred-capture-surface">KSPROPERTY_PREFERRED_CAPTURE_SURFACE</a>

