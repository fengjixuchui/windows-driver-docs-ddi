---
UID: NS:ks.__unnamed_union_9
title: KSPROPERTY_BOUNDS_LONG (ks.h)
description: The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property.
old-location: stream\ksproperty_bounds_long.htm
tech.root: stream
ms.assetid: 16804ff1-8531-48aa-baf6-b89ccfe25d07
ms.date: 04/23/2018
keywords: ["KSPROPERTY_BOUNDS_LONG structure"]
ms.keywords: "*PKSPROPERTY_BOUNDS_LONG, KSPROPERTY_BOUNDS_LONG, KSPROPERTY_BOUNDS_LONG union [Streaming Media Devices], PKSPROPERTY_BOUNDS_LONG, PKSPROPERTY_BOUNDS_LONG union pointer [Streaming Media Devices], ks-struct_805e1a44-91bb-45be-a99d-174e98639d9e.xml, ks/KSPROPERTY_BOUNDS_LONG, ks/PKSPROPERTY_BOUNDS_LONG, stream.ksproperty_bounds_long"
f1_keywords:
 - "ks/KSPROPERTY_BOUNDS_LONG"
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
- KSPROPERTY_BOUNDS_LONG
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_BOUNDS_LONG, *PKSPROPERTY_BOUNDS_LONG
---

# KSPROPERTY_BOUNDS_LONG structure


## -description


The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property.


## -struct-fields




### -field _SIGNED

 


### -field _SIGNED.SignedMinimum

 


### -field _SIGNED.SignedMaximum

 


### -field SignedMinimum

Specifies a minimum bound as a signed 32-bit value.


### -field SignedMaximum

Specifies a maximum bound as a signed 32-bit value.


### -field _UNSIGNED

 


### -field _UNSIGNED.UnsignedMinimum

 


### -field _UNSIGNED.UnsignedMaximum

 


### -field UnsignedMinimum

Specifies a minimum bound as an unsigned 32-bit value.


### -field UnsignedMaximum

Specifies a maximum bound as an unsigned 32-bit value.


## -remarks



This structure specifies a range of 32-bit values for a property. Use only when the <b>MembersFlags</b> member of the relevant <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a> is set to KSPROPERTY_MEMBER_RANGES. Use this structure in the <b>Members</b> array in the relevant <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a> structure.

See the Testcap sample in the Windows Driver Kit (WDK) for examples of usage.

Also see related information in <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-properties">KS Properties</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a>
 

 

