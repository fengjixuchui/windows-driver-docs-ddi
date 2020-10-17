---
UID: NS:ntddk._SOC_SUBSYSTEM_FAILURE_DETAILS
title: _SOC_SUBSYSTEM_FAILURE_DETAILS (ntddk.h)
description: The SOC_SUBSYSTEM_FAILURE_DETAILS structure holds information related to a System on a Chip (SoC) bug code.
old-location: whea\soc_subsystem_failure_details.htm
tech.root: whea
ms.assetid: 416F9A0C-0A86-4FAA-9052-5D37D29C464D
ms.date: 02/20/2018
keywords: ["SOC_SUBSYSTEM_FAILURE_DETAILS structure"]
ms.keywords: "*PSOC_SUBSYSTEM_FAILURE_DETAILS, PSOC_SUBSYSTEM_FAILURE_DETAILS, PSOC_SUBSYSTEM_FAILURE_DETAILS structure pointer [WHEA Drivers and Applications], SOC_SUBSYSTEM_FAILURE_DETAILS, SOC_SUBSYSTEM_FAILURE_DETAILS structure [WHEA Drivers and Applications], _SOC_SUBSYSTEM_FAILURE_DETAILS, ntddk/PSOC_SUBSYSTEM_FAILURE_DETAILS, ntddk/SOC_SUBSYSTEM_FAILURE_DETAILS, whea.soc_subsystem_failure_details"
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: SOC_SUBSYSTEM_FAILURE_DETAILS, *PSOC_SUBSYSTEM_FAILURE_DETAILS
f1_keywords:
 - _SOC_SUBSYSTEM_FAILURE_DETAILS
 - ntddk/_SOC_SUBSYSTEM_FAILURE_DETAILS
 - PSOC_SUBSYSTEM_FAILURE_DETAILS
 - ntddk/PSOC_SUBSYSTEM_FAILURE_DETAILS
 - SOC_SUBSYSTEM_FAILURE_DETAILS
 - ntddk/SOC_SUBSYSTEM_FAILURE_DETAILS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - SOC_SUBSYSTEM_FAILURE_DETAILS
---

# _SOC_SUBSYSTEM_FAILURE_DETAILS structure


## -description

The   <b>SOC_SUBSYSTEM_FAILURE_DETAILS</b> structure holds information related to a System on a Chip (SoC) bug code.

These bug codes store information in a 
  this structure.
<ul>
<li>
<a href="/windows-hardware/drivers/debugger/bug-check-0x14b--soc-subsystem-failure">Bug    Check 0x14B SOC_SUBSYSTEM_FAILURE</a>
</li>
<li>
<a href="/windows-hardware/drivers/debugger/bug-check-0x15d-soc-subsystem-failure-livedump">Bug Check 0x15D SOC_SUBSYSTEM_FAILURE_LIVEDUMP</a>
</li>
</ul>

## -struct-fields

### -field SubsysType

A value in the <a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_soc_subsystem_type">SOC_SYBSYSTEM_TYPE</a> enumeration or a vendor-defined subsystem type. Subsystem types in the range 0x10000 through 0x80000000 are reserved for independent hardware vendors.

### -field FirmwareVersion

A vendor-defined SoC firmware version number.

### -field HardwareVersion

A  vendor-defined SoC hardware version number.

### -field UnifiedFailureRegionSize

The size, in bytes, of the <b>UnifiedFailureRegion</b> string including the <b>NULL</b> terminator.

### -field UnifiedFailureRegion

A null-terminated string, defined by the vendor, that  contains classification details about the error that occurred.