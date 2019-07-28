---
UID: NS:ks.__unnamed_struct_7
title: KSPROPERTY_DESCRIPTION (ks.h)
description: The KSPROPERTY_DESCRIPTION structure specifies the size and type of values contained in a specific property.
old-location: stream\ksproperty_description.htm
tech.root: stream
ms.assetid: d3d59dca-7214-493c-bb70-4391696fe017
ms.date: 04/23/2018
ms.keywords: "*PKSPROPERTY_DESCRIPTION, KSPROPERTY_DESCRIPTION, KSPROPERTY_DESCRIPTION structure [Streaming Media Devices], PKSPROPERTY_DESCRIPTION, PKSPROPERTY_DESCRIPTION structure pointer [Streaming Media Devices], ks-struct_37ee8090-f90e-40a9-8731-3521d1d3a157.xml, ks/KSPROPERTY_DESCRIPTION, ks/PKSPROPERTY_DESCRIPTION, stream.ksproperty_description"
ms.topic: struct
f1_keywords:
 - "ks/KSPROPERTY_DESCRIPTION"
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
- KSPROPERTY_DESCRIPTION
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_DESCRIPTION, *PKSPROPERTY_DESCRIPTION
---

# KSPROPERTY_DESCRIPTION structure


## -description


The KSPROPERTY_DESCRIPTION structure specifies the size and type of values contained in a specific property.


## -struct-fields




### -field AccessFlags

Specifies the access allowed to this property. A basic-support request sets this member to the bitwise OR of the flags for all the access types that the handler supports for this property. For a list of possible flag values, see <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>.


### -field DescriptionSize

Specifies total size in bytes of the KSPROPERTY_DESCRIPTION structure and any values entries that follow it. If the basic-support property request returns no values entries, this member is the size of KSPROPERTY_DESCRIPTION.


### -field PropTypeSet

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksidentifier">KSIDENTIFIER</a>. If supported by the specific property, specifies the type of values contained in this property. This group is uniquely specified by a GUID, such that new types of values may be created without overlapping with extensions to this set. The value types indicate the type of the value (like VT_BOOL, VT_UI4 in the standard set). This is GUID_NULL, with an identifier of zero, if values information is not supported by this property.


### -field MembersListCount

Specifies the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a> structures to follow this header.


### -field Reserved

Reserved for future use. Set to zero.


## -remarks



A driver returns the <b>KSPROPERTY_DESCRIPTION</b> structure in response to a basic support property request from a client.

The property values type set is specified by a KSIDENTIFIER structure. The basic set supported is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-general">KSPROPSETID_General</a>. The identifiers within that set are the standard VARENUM types used for OLE.

The values information that may follow the KSPROPERTY_DESCRIPTION structure is described by a list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a> structures, each of which contains data range information.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-properties">KS Properties</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksidentifier">KSIDENTIFIER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_item">KSPROPERTY_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a>
 

 

