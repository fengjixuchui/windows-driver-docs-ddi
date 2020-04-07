---
UID: NC:d3dkmthk.PFND3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
title: PFND3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE (d3dkmthk.h)
description: Implemented by the client driver to submit a signal to the hardware queue.
ms.assetid: 4d3b171d-10f1-43a7-ba73-3864d9a590a9
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE"
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
- PFND3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE callback function

## -description

Implemented by the client driver to submit a signal to the hardware queue.

## -prototype

```cpp
//Declaration

PFND3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE Pfnd3dkmtSubmitsignalsyncobjectstohwqueue;

// Definition

NTSTATUS Pfnd3dkmtSubmitsignalsyncobjectstohwqueue
(
	CONST D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE *
)
{...}

PFND3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE


```

## -parameters

### -param D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE *

Pointer to a [D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitsignalsyncobjectstohwqueue.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitsignalsyncobjectstohwqueue.md) and then calling Pfnd3dkmtSubmitsignalsyncobjectstohwqueue.

