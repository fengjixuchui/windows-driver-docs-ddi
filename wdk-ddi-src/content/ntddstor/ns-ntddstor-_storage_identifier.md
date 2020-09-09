---
UID: NS:ntddstor._STORAGE_IDENTIFIER
title: _STORAGE_IDENTIFIER (ntddstor.h)
description: The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor.
old-location: storage\storage_identifier.htm
tech.root: storage
ms.assetid: f2b0610a-dffa-48fb-bc5a-355fa9f05770
ms.date: 03/29/2018
keywords: ["STORAGE_IDENTIFIER structure"]
ms.keywords: "*PSTORAGE_IDENTIFIER, PSTORAGE_IDENTIFIER, PSTORAGE_IDENTIFIER structure pointer [Storage Devices], STORAGE_IDENTIFIER, STORAGE_IDENTIFIER structure [Storage Devices], _STORAGE_IDENTIFIER, ntddstor/PSTORAGE_IDENTIFIER, ntddstor/STORAGE_IDENTIFIER, storage.storage_identifier, structs-general_29c666d7-3e61-44fe-a36e-979418dbb958.xml"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
req.typenames: STORAGE_IDENTIFIER, *PSTORAGE_IDENTIFIER
f1_keywords:
 - _STORAGE_IDENTIFIER
 - ntddstor/_STORAGE_IDENTIFIER
 - PSTORAGE_IDENTIFIER
 - ntddstor/PSTORAGE_IDENTIFIER
 - STORAGE_IDENTIFIER
 - ntddstor/STORAGE_IDENTIFIER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_IDENTIFIER
---

# _STORAGE_IDENTIFIER structure


## -description

The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor.

## -struct-fields

### -field CodeSet

Specifies the code set used by a SCSI identification descriptor to identify a logical unit.

### -field Type

Contains an enumerator value of type <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566990(v=vs.85)">STORAGE_IDENTIFIER_TYPE</a> that indicates the identifier type.

### -field IdentifierSize

Specifies the size in bytes of the identifier.

### -field NextOffset

Specifies the offset in bytes from the current descriptor to the next descriptor.

### -field Association

Contains an enumerator value of type <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566349(v=vs.85)">STORAGE_ASSOCIATION_TYPE</a> that indicates whether the descriptor identifies a device or a port.

### -field Identifier

Contains the identifier associated with this descriptor.

## -remarks

Every device identification page (page code 0x83) of SCSI vital product data contains a series of identification descriptors. The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566349(v=vs.85)">STORAGE_ASSOCIATION_TYPE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566990(v=vs.85)">STORAGE_IDENTIFIER_TYPE</a>

