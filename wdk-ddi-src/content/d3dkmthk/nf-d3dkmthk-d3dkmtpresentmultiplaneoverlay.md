---
UID: NF:d3dkmthk.D3DKMTPresentMultiPlaneOverlay
title: D3DKMTPresentMultiPlaneOverlay function (d3dkmthk.h)
description: Copies content from a source multiplane overlay allocation to a destination allocation.
ms.assetid: acf7922c-f3f8-4873-b8f0-df30700a32db
ms.date: 10/19/2018
keywords: ["D3DKMTPresentMultiPlaneOverlay function"]
f1_keywords:
 - "d3dkmthk/D3DKMTPresentMultiPlaneOverlay"
 - "D3DKMTPresentMultiPlaneOverlay"
ms.keywords: D3DKMTPresentMultiPlaneOverlay
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver:
req.umdf-ver:
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- Gdi32.dll
api_name: 
- D3DKMTPresentMultiPlaneOverlay
targetos: Windows
dev_langs:
 - c++
ms.custom: RS5
tech.root: display
---

# D3DKMTPresentMultiPlaneOverlay function


## -description

Copies content from a source multiplane overlay allocation to a destination allocation.

## -parameters

### -param Arg1

*\_In\_* *pPresent*

Pointer to a [D3DKMT_PRESENT_MULTIPLANE_OVERLAY](ns-d3dkmthk-d3dkmt_present_multiplane_overlay.md) structure.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

[D3DKMT_PRESENT_MULTIPLANE_OVERLAY](ns-d3dkmthk-d3dkmt_present_multiplane_overlay.md)
