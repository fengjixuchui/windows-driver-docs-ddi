---
UID: NS:d3dkmddi._DXGK_UPDATEPAGETABLEFLAGS
title: _DXGK_UPDATEPAGETABLEFLAGS (d3dkmddi.h)
description: DXGK_UPDATEPAGETABLEFLAGS is used as part of a page table update operation.
old-location: display\dxgk_updatepagetableflags.htm
ms.assetid: E0E1CDE7-F1BF-44C8-A320-9BD90788679F
ms.date: 05/10/2018
keywords: ["DXGK_UPDATEPAGETABLEFLAGS structure"]
ms.keywords: DXGK_UPDATEPAGETABLEFLAGS, DXGK_UPDATEPAGETABLEFLAGS structure [Display Devices], _DXGK_UPDATEPAGETABLEFLAGS, d3dkmddi/DXGK_UPDATEPAGETABLEFLAGS, display.dxgk_updatepagetableflags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: DXGK_UPDATEPAGETABLEFLAGS
f1_keywords:
 - _DXGK_UPDATEPAGETABLEFLAGS
 - d3dkmddi/_DXGK_UPDATEPAGETABLEFLAGS
 - DXGK_UPDATEPAGETABLEFLAGS
 - d3dkmddi/DXGK_UPDATEPAGETABLEFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_UPDATEPAGETABLEFLAGS
---

# _DXGK_UPDATEPAGETABLEFLAGS structure


## -description

<b>DXGK_UPDATEPAGETABLEFLAGS</b> is used as part of a page table update operation.

## -struct-fields

### -field Repeat

When set to <b>TRUE</b>, page table entries will point to a single page table entry value that needs to be replicated to all page table entries being updated.

### -field InitialUpdate

Indicates that the page table is initialized very first time after being made resident in memory.

### -field NotifyEviction

Indicates that the page table is about to be evicted.

### -field Use64KBPages

Indicates that page table entries  point to page tables pointing to 64 KB pages.

### -field Reserved

This member is reserved and should be set to zero.

