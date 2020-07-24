---
UID: NS:d3dkmddi._DXGK_TRANSFERVIRTUALFLAGS
title: _DXGK_TRANSFERVIRTUALFLAGS (d3dkmddi.h)
description: DXGK_TRANSFERVIRTUALFLAGS is used as part of an allocation transfer operation.
old-location: display\dxgk_transfervirtualflags.htm
ms.assetid: E5323A30-5BBE-4084-9F99-91FBDD680C12
ms.date: 05/10/2018
keywords: ["_DXGK_TRANSFERVIRTUALFLAGS structure"]
ms.keywords: DXGK_TRANSFERVIRTUALFLAGS, DXGK_TRANSFERVIRTUALFLAGS structure [Display Devices], _DXGK_TRANSFERVIRTUALFLAGS, d3dkmddi/DXGK_TRANSFERVIRTUALFLAGS, display.dxgk_transfervirtualflags
f1_keywords:
 - "d3dkmddi/DXGK_TRANSFERVIRTUALFLAGS"
 - "DXGK_TRANSFERVIRTUALFLAGS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_TRANSFERVIRTUALFLAGS
targetos: Windows
tech.root: display
req.typenames: DXGK_TRANSFERVIRTUALFLAGS
---

# _DXGK_TRANSFERVIRTUALFLAGS structure


## -description


<b>DXGK_TRANSFERVIRTUALFLAGS</b> is used as part of an allocation transfer operation.


## -struct-fields




### -field Src64KBPages

When set, the source page tables are mapped to  64KB pages.


### -field Dst64KBPages

When set, the destination page tables are mapped to  64KB pages.


### -field Reserved

This member is reserved and should be set to zero.


### -field Flags

The consolidated value of the structure flags.

