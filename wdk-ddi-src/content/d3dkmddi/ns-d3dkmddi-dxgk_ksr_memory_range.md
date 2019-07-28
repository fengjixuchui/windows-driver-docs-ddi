---
UID: NS:d3dkmddi._DXGK_KSR_MEMORY_RANGE
title: DXGK_KSR_MEMORY_RANGE
author: windows-driver-content
description: The kernel soft reboot (KSR) memory range.
tech.root: display
ms.assetid: 6131bf6c-c18f-4ff6-ae89-b39528c77be2
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_KSR_MEMORY_RANGE"
ms.keywords: DXGK_KSR_MEMORY_RANGE, DXGK_KSR_MEMORY_RANGE, *PDXGK_KSR_MEMORY_RANGE, 
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_KSR_MEMORY_RANGE, *PDXGK_KSR_MEMORY_RANGE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3dkmddi.h
api_name: 
 - DXGK_KSR_MEMORY_RANGE
product:
- Windows
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
---

# DXGK_KSR_MEMORY_RANGE structure

## -description

The kernel soft reboot (KSR) memory range.

## -struct-fields

### -field MemoryRangeDesc

Provides a description of the memory range.

Bits 0-39: Physical page number of the first page. This is the physical page address shifted 12 bits right.

Bits 40-63: Number of pages.

## -remarks

## -see-also
