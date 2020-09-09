---
UID: NS:d3dkmddi._DXGKCB_GETHANDLEDATAFLAGS
title: _DXGKCB_GETHANDLEDATAFLAGS (d3dkmddi.h)
description: The DXGKCB_GETHANDLEDATAFLAGS structure indicates if allocations belong to a resource.
old-location: display\dxgkcb_gethandledataflags.htm
ms.assetid: 01689a2f-115a-4db8-b53d-38717c10a0ff
ms.date: 05/10/2018
keywords: ["DXGKCB_GETHANDLEDATAFLAGS structure"]
ms.keywords: DXGKCB_GETHANDLEDATAFLAGS, DXGKCB_GETHANDLEDATAFLAGS structure [Display Devices], DmStructs_a0288df8-0513-4823-9445-cd86ff45a186.xml, _DXGKCB_GETHANDLEDATAFLAGS, d3dkmddi/DXGKCB_GETHANDLEDATAFLAGS, display.dxgkcb_gethandledataflags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
tech.root: display
req.typenames: DXGKCB_GETHANDLEDATAFLAGS
f1_keywords:
 - _DXGKCB_GETHANDLEDATAFLAGS
 - d3dkmddi/_DXGKCB_GETHANDLEDATAFLAGS
 - DXGKCB_GETHANDLEDATAFLAGS
 - d3dkmddi/DXGKCB_GETHANDLEDATAFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_GETHANDLEDATAFLAGS
---

# _DXGKCB_GETHANDLEDATAFLAGS structure


## -description

The DXGKCB_GETHANDLEDATAFLAGS structure indicates if allocations belong to a resource.

## -struct-fields

### -field DeviceSpecific

A UINT value that specifies whether allocations belong to a resource. If this member is set, the allocations belong to a resource. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A member in the union that DXGKCB_GETHANDLEDATAFLAGS contains that can hold a 32-bit value that indicates if allocations belong to a resource.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_gethandledata">DXGKARGCB_GETHANDLEDATA</a>

