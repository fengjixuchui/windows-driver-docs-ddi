---
UID: NE:storduid._DUID_MATCH_STATUS
title: _DUID_MATCH_STATUS (storduid.h)
description: The DUID_MATCH_STATUS enumeration lists the status values that the CompareStorageDuids routine returns.
old-location: storage\duid_match_status.htm
tech.root: storage
ms.assetid: 61a60e77-387c-42d6-b56b-694ce0c86570
ms.date: 03/29/2018
keywords: ["DUID_MATCH_STATUS enumeration"]
ms.keywords: DUID_MATCH_STATUS, DUID_MATCH_STATUS enumeration [Storage Devices], DuidErrorGeneral, DuidErrorInvalidDeviceDescSize, DuidErrorInvalidDeviceIdDescSize, DuidErrorInvalidDuid, DuidErrorInvalidLayoutSigSize, DuidErrorInvalidLayoutSigVersion, DuidErrorMaximum, DuidErrorMissingDuid, DuidErrorVersionMismatch, DuidExactMatch, DuidNoMatch, DuidSubIdMatch, _DUID_MATCH_STATUS, storage.duid_match_status, storduid/DUID_MATCH_STATUS, storduid/DuidErrorGeneral, storduid/DuidErrorInvalidDeviceDescSize, storduid/DuidErrorInvalidDeviceIdDescSize, storduid/DuidErrorInvalidDuid, storduid/DuidErrorInvalidLayoutSigSize, storduid/DuidErrorInvalidLayoutSigVersion, storduid/DuidErrorMaximum, storduid/DuidErrorMissingDuid, storduid/DuidErrorVersionMismatch, storduid/DuidExactMatch, storduid/DuidNoMatch, storduid/DuidSubIdMatch, structs-general_8e33f54f-7115-42c2-aa06-112c79f9c392.xml
req.header: storduid.h
req.include-header: Storduid.h
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
req.typenames: DUID_MATCH_STATUS
f1_keywords:
 - _DUID_MATCH_STATUS
 - storduid/_DUID_MATCH_STATUS
 - DUID_MATCH_STATUS
 - storduid/DUID_MATCH_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storduid.h
api_name:
 - DUID_MATCH_STATUS
---

# _DUID_MATCH_STATUS enumeration


## -description

The DUID_MATCH_STATUS enumeration lists the status values that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storduid/nf-storduid-comparestorageduids">CompareStorageDuids</a> routine returns.

## -enum-fields

### -field DuidExactMatch

All fields in the two Device Unique Identifiers (DUIDs) match exactly.

### -field DuidSubIdMatch

Either the serial number or one of the unique sub-IDs matches. The two DUIDs probably represent the same device.

### -field DuidNoMatch

None of the sub-IDs match in page 83h of the vital product data (VPD). None of the non-VPD data matches.

### -field DuidErrorGeneral

An error occurred for an unspecified cause.

### -field DuidErrorMissingDuid

One of the two DUIDs to compare is missing.

### -field DuidErrorVersionMismatch

The two DUIDs to compare do not have the same version.

### -field DuidErrorInvalidDuid

At least one of the two DUIDs to compare is invalid.

### -field DuidErrorInvalidDeviceIdDescSize

At least one of the two DUIDs to compare contains an invalid device ID descriptor (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_id_descriptor">STORAGE_DEVICE_ID_DESCRIPTOR</a>). This descriptor reports VPD data.

### -field DuidErrorInvalidDeviceDescSize

At least one of the two DUIDs to compare contains an invalid device descriptor (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a>). This descriptor reports non-VPD inquiry data..

### -field DuidErrorInvalidLayoutSigSize

At least one of the two DUIDs to compare contains an invalid drive layout signature size.

### -field DuidErrorInvalidLayoutSigVersion

At least one of the two DUIDs to compare contains an invalid drive layout signature.

### -field DuidErrorMaximum

This value delimits the upper limit of the enumeration values in this enumeration. This value allows a DUID consumer to create a loop that tests for all valid error values that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storduid/nf-storduid-comparestorageduids">CompareStorageDuids</a> routine returns. As new identifier data is added to future versions of the DUID, new error values will specify which parts of the DUID are not well-formed.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storduid/nf-storduid-comparestorageduids">CompareStorageDuids</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_id_descriptor">STORAGE_DEVICE_ID_DESCRIPTOR</a>

