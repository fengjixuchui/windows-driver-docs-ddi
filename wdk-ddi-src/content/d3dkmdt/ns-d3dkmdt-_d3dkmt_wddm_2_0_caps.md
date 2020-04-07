---
UID: NS:d3dkmdt._D3DKMT_WDDM_2_0_CAPS
title: _D3DKMT_WDDM_2_0_CAPS (d3dkmdt.h)
description: Indicates the capabilities for Windows Display Driver Model v2.0.
ms.assetid: 4a073daa-4233-4c38-bcef-86dc04d00352
ms.date: 10/19/2018
keywords: ["_D3DKMT_WDDM_2_0_CAPS structure"]
f1_keywords:
 - "d3dkmdt/_D3DKMT_WDDM_2_0_CAPS"
ms.keywords: _D3DKMT_WDDM_2_0_CAPS, D3DKMT_WDDM_2_0_CAPS,
req.header: d3dkmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_WDDM_2_0_CAPS
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- _D3DKMT_WDDM_2_0_CAPS
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_WDDM_2_0_CAPS structure

## -description

Indicates the capabilities for Windows Display Driver Model v2.0.

## -struct-fields

### -field Support64BitAtomics

Supports 64-bit atomics.

### -field GpuMmuSupported

Supports GPU memory management.

### -field IoMmuSupported

Supports input/output memory management.

### -field FlipOverwriteSupported

Supports flip overwrite.

### -field SupportContextlessPresent

Supports contextless present display.

### -field SupportSurpriseRemoval

Supports surprise removal.

### -field Reserved

Reserved.

### -field Value

Value.

