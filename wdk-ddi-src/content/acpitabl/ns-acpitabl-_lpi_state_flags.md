---
UID: NS:acpitabl._LPI_STATE_FLAGS
title: _LPI_STATE_FLAGS (acpitabl.h)
description: Defines LPI state flags, either as a structure or as an integer.
old-location: acpi\lpi_state_flags.htm
tech.root: acpi
ms.assetid: 3A9DECE8-E85A-49D5-8AF1-6C7BA8B1AB7D
ms.date: 02/15/2018
keywords: ["LPI_STATE_FLAGS structure"]
ms.keywords: "*PLPI_STATE_FLAGS, LPI_STATE_FLAGS, LPI_STATE_FLAGS union [ACPI Devices], _LPI_STATE_FLAGS, acpi.lpi_state_flags, acpitabl/LPI_STATE_FLAGS"
req.header: acpitabl.h
req.include-header: Acpitabl.h
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
req.typenames: LPI_STATE_FLAGS, *PLPI_STATE_FLAGS
f1_keywords:
 - _LPI_STATE_FLAGS
 - acpitabl/_LPI_STATE_FLAGS
 - PLPI_STATE_FLAGS
 - acpitabl/PLPI_STATE_FLAGS
 - LPI_STATE_FLAGS
 - acpitabl/LPI_STATE_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - LPI_STATE_FLAGS
---

# _LPI_STATE_FLAGS structure


## -description

Defines LPI state flags, either as a structure or as an integer.

## -struct-fields

### -field Disabled

### -field CounterUnavailable

### -field Reserved

### -field AsUlong

An LPI state as an integer. 


#### - {
        ULONG Disabled:1;
        ULONG CounterUnavailable:1;
        ULONG Reserved:30;
    }

An LPI state as a structure.

