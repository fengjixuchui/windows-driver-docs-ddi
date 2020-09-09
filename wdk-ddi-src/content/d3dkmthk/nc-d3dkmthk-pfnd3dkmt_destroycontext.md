---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYCONTEXT
title: PFND3DKMT_DESTROYCONTEXT (d3dkmthk.h)
description: Implemented by the client driver to destroy the specified graphics processing unit (GPU) context.
ms.assetid: 6b88e83a-a211-417e-a34d-ed98ae9b4b4b
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYCONTEXT callback function"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_DESTROYCONTEXT
 - d3dkmthk/PFND3DKMT_DESTROYCONTEXT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_DESTROYCONTEXT
dev_langs:
 - c++
---

# PFND3DKMT_DESTROYCONTEXT callback function


## -description

Implemented by the client driver to destroy the specified graphics processing unit (GPU) context.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_DESTROYCONTEXT](ns-d3dkmthk-_d3dkmt_destroycontext.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYCONTEXT Pfnd3dkmtDestroycontext; 

// Definition

NTSTATUS Pfnd3dkmtDestroycontext 
(
	const D3DKMT_DESTROYCONTEXT *
)
{...}

```

