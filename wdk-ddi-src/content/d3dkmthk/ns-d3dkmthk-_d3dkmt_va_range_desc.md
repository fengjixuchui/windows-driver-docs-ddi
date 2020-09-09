---
UID: NS:d3dkmthk._D3DKMT_VA_RANGE_DESC
title: _D3DKMT_VA_RANGE_DESC (d3dkmthk.h)
description: The virtual address (VA) range description.
ms.assetid: 96c89737-4994-46fe-af09-16339226675c
ms.date: 10/19/2018
keywords: ["D3DKMT_VA_RANGE_DESC structure"]
ms.keywords: _D3DKMT_VA_RANGE_DESC, D3DKMT_VA_RANGE_DESC,
req.header: d3dkmthk.h
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
req.typenames: D3DKMT_VA_RANGE_DESC
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_VA_RANGE_DESC
 - d3dkmthk/_D3DKMT_VA_RANGE_DESC
 - D3DKMT_VA_RANGE_DESC
 - d3dkmthk/D3DKMT_VA_RANGE_DESC
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_VA_RANGE_DESC
dev_langs:
 - c++
---

# _D3DKMT_VA_RANGE_DESC structure


## -description

The virtual address (VA) range description.

## -struct-fields

### -field VadAddress

[in] The video acceleration display (VAD) address.

### -field VaRangeIndex

[in] The virtual address range index.

### -field PhysicalAdapterIndex

[in] The physical adapter index in the LDA (linked display adapter) chain.

### -field StartAddress

[out] The start address.

### -field EndAddress

[out] The end address.

### -field DriverProtection

[out] The driver protection.

### -field OwnerType

[out] A VIDMM_VAD_OWNER_TYPE owner type.

### -field pOwner

[out] Pointer to the owner.

### -field OwnerOffset

[out] The owner offset.

### -field Protection

 
[out] A D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE protection type.

## -remarks

## -see-also

