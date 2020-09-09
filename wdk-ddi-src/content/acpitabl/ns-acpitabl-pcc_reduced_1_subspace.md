---
UID: NS:acpitabl._PCC_REDUCED_1_SUBSPACE
title: _PCC_REDUCED_1_SUBSPACE (acpitabl.h)
ms.date: 08/12/2020
ms.keywords: _PCC_REDUCED_1_SUBSPACE, PCC_REDUCED_1_SUBSPACE, *PPCC_REDUCED_1_SUBSPACE
description: Contains information about the the ACPI Platform Communication Channel (PCC) HW-reduced Type 1 subspace.
tech.root: acpi
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acpitabl.h
req.include-header: Acpitabl.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: PCC_REDUCED_1_SUBSPACE, *PPCC_REDUCED_1_SUBSPACE
req.umdf-ver: 
req.unicode-ansi: 
targetos: Windows
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _PCC_REDUCED_1_SUBSPACE
 - PCC_REDUCED_1_SUBSPACE
f1_keywords:
 - _PCC_REDUCED_1_SUBSPACE
 - acpitabl/_PCC_REDUCED_1_SUBSPACE
 - PPCC_REDUCED_1_SUBSPACE
 - acpitabl/PPCC_REDUCED_1_SUBSPACE
 - PCC_REDUCED_1_SUBSPACE
 - acpitabl/PCC_REDUCED_1_SUBSPACE
---

# _PCC_REDUCED_1_SUBSPACE structure


## -description

The **PCC_REDUCED_1_SUBSPACE** structure contains information about the the ACPI Platform Communication Channel (PCC) HW-reduced Type 1 subspace.

## -struct-fields

### -field Header

The **PCC_SUBSPACE_HEADER** header.

### -field PlatformInterruptGsiv

The PCC platform global system interrupt vector (GSIV).

### -field PlatformInterruptPolarity

The PCC platform interrupt polarity value (one of **PCC_PLATFORM_INTERRUPT_POLARITY_XXX**).

### -field PlatformInterruptMode

The PCC platform interrupt mode (must be **PCC_PLATFORM_INTERRUPT_MODE_EDGE_TRIGGERED**).

### -field Reserved1

Reserved for future use.

### -field PlatformInterruptFlags

The PCC platform interrupt flags.

### -field Reserved2

Reserved for future use.

### -field BaseAddress

The **PHYSICAL_ADDRESS** base address.

### -field Length

The length value.

### -field DoorbellRegister

The **GEN_ADDR** doorbell register.

### -field DoorbellPreserve

The doorbell preserve mask.

### -field DoorbellWrite

The doorbell write mask.

### -field NominalLatency

The nominal latency value.

### -field MaximumPeriodicAccessRate

The maximum periodic access rate value.

### -field MinimumRequestTurnaroundTime

The minimum request turnaround time value.

## -remarks

## -see-also

