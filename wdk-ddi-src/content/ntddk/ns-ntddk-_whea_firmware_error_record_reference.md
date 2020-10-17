---
UID: NS:ntddk._WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
title: _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE (ntddk.h)
description: The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes a reference to a firmware error record that is specific to the Itanium processor architecture.
old-location: whea\whea_firmware_error_record_reference.htm
tech.root: whea
ms.assetid: 950a9b93-ef69-4075-9231-eb481a53c617
ms.date: 02/20/2018
keywords: ["WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure"]
ms.keywords: "*PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE, *PWHEA_FIRMWARE_RECORD, PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE, PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure pointer [WHEA Drivers and Applications], WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure [WHEA Drivers and Applications], WHEA_FIRMWARE_RECORD, _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, ntddk/PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE, ntddk/WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, whea.whea_firmware_error_record_reference, whearef_b43d8c6f-f768-47a1-9494-4a4bfac7d586.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.typenames: WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, *PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE
f1_keywords:
 - _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - ntddk/_WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - ntddk/PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - ntddk/WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
---

# _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure


## -description

The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes a reference to a firmware error record that is specific to the Itanium processor architecture.

## -struct-fields

### -field Type

The type of firmware error record. This member is always set to WHEA_FIRMWARE_RECORD_TYPE_IPFSAL.

### -field Reserved

Reserved for system use.

### -field FirmwareRecordId

The identifier of the firmware error record.

## -remarks

The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes the data that is contained in an Itanium processor firmware error record reference section of an <a href="/windows-hardware/drivers/whea/error-records">error record</a>. An error record contains an Itanium processor firmware error record reference section only if the <b>SectionType </b>member of one of the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains FIRMWARE_ERROR_RECORD_REFERENCE_GUID.

The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure contains a reference to a SAL error record that was created by the system firmware. For more information about the format of a SAL error record, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=72212">Intel Itanium Processor Family System Abstraction Layer Specification</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>