---
UID: NE:d3dumddi.D3DDDI_COPY_FLAGS
title: D3DDDI_COPY_FLAGS (d3dumddi.h)
description: Specifies how to handle the existing contents of a resource during a copy or update operation of a region within that resource.
old-location: display\d3dddi_copy_flags.htm
tech.root: display
ms.assetid: 6186dac4-4797-48f2-bb32-40a0d501bac7
ms.date: 05/10/2018
ms.keywords: D3DDDI_COPY_DISCARD, D3DDDI_COPY_FLAGS, D3DDDI_COPY_FLAGS enumeration [Display Devices], D3DDDI_COPY_NO_OVERWRITE, d3dumddi/D3DDDI_COPY_DISCARD, d3dumddi/D3DDDI_COPY_FLAGS, d3dumddi/D3DDDI_COPY_NO_OVERWRITE, display.d3dddi_copy_flags
ms.topic: enum
f1_keywords:
 - "d3dumddi/D3DDDI_COPY_FLAGS"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dumddi.h
api_name:
- D3DDDI_COPY_FLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_COPY_FLAGS
---

# D3DDDI_COPY_FLAGS enumeration


## -description


Specifies how to handle the existing contents of a resource during a copy or update operation of a region within that resource.


## -enum-fields




### -field D3DDDI_COPY_NO_OVERWRITE

The caller guarantees that the portion of the surface that is being written to with new data is not currently being referenced or accessed by any previous render operation. The driver can take advantage of this capability to optimize performance and memory usage.


### -field D3DDDI_COPY_DISCARD

The user-mode display driver can discard previous contents of the entire resource. The driver can take advantage of this capability to optimize performance and memory usage.

