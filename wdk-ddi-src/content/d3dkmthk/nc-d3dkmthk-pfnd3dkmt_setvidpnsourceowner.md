---
UID: NC:d3dkmthk.PFND3DKMT_SETVIDPNSOURCEOWNER
title: PFND3DKMT_SETVIDPNSOURCEOWNER (d3dkmthk.h)
description: The PFND3DKMT_SETVIDPNSOURCEOWNER callback function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
ms.assetid: 3773cd36-d9ba-46b4-9851-389da4f37d69
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETVIDPNSOURCEOWNER callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SETVIDPNSOURCEOWNER"
 - "PFND3DKMT_SETVIDPNSOURCEOWNER"
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
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
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_SETVIDPNSOURCEOWNER
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SETVIDPNSOURCEOWNER callback function

## -description

The PFND3DKMT_SETVIDPNSOURCEOWNER callback function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETVIDPNSOURCEOWNER Pfnd3dkmtSetvidpnsourceowner; 

// Definition

NTSTATUS Pfnd3dkmtSetvidpnsourceowner 
(
	const D3DKMT_SETVIDPNSOURCEOWNER *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
