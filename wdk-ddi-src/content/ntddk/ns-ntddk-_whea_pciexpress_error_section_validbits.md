---
UID: NS:ntddk._WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
title: _WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS (ntddk.h)
description: The WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PCIEXPRESS_ERROR_SECTION structure contain valid data.
old-location: whea\whea_pciexpress_error_section_validbits.htm
tech.root: whea
ms.assetid: 1c4c3e9c-32a2-405a-b27d-98f8da715626
ms.date: 02/20/2018
keywords: ["WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS structure"]
ms.keywords: "*PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, *PWHEA_PCIEXPRESS_ERROR_VALIDBITS, PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], WHEA_PCIEXPRESS_ERROR_VALIDBITS, _WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, ntddk/WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, whea.whea_pciexpress_error_section_validbits, whearef_9b6e3f92-4939-401a-9da2-e2ece44b1e98.xml"
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
req.typenames: WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, *PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
f1_keywords:
 - _WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
 - ntddk/_WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
 - PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
 - ntddk/PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
 - WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
 - ntddk/WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
---

# _WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS structure


## -description

The WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union describes which members of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pciexpress_error_section">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure contain valid data.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.PortType

A single bit that indicates that the <b>PortType</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.

### -field DUMMYSTRUCTNAME.Version

A single bit that indicates that the <b>Version</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.

### -field DUMMYSTRUCTNAME.CommandStatus

A single bit that indicates that the <b>CommandStatus</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.

### -field DUMMYSTRUCTNAME.DeviceId

A single bit that indicates that the <b>DeviceId</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.

### -field DUMMYSTRUCTNAME.DeviceSerialNumber

A single bit that indicates that the <b>DeviceSerialNumber</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.

### -field DUMMYSTRUCTNAME.BridgeControlStatus

A single bit that indicates that the <b>BridgeControlStatus</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.

### -field DUMMYSTRUCTNAME.ExpressCapability

A single bit that indicates that the <b>ExpressCapability</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.

### -field DUMMYSTRUCTNAME.AerInfo

A single bit that indicates that the <b>AerInfo</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.

### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.

### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union.

## -remarks

A WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union is contained within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pciexpress_error_section">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pciexpress_error_section">WHEA_PCIEXPRESS_ERROR_SECTION</a>

