---
UID: NC:d3dkmthk.PFND3DKMT_SETFSEBLOCK
title: PFND3DKMT_SETFSEBLOCK (d3dkmthk.h)
description: The PFND3DKMT_SETFSEBLOCK callback function sets FSE block.
ms.assetid: b0a3d6d7-9b7d-46eb-b3a5-a2faf0e1c9a6
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETFSEBLOCK callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SETFSEBLOCK"
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
- PFND3DKMT_SETFSEBLOCK
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SETFSEBLOCK callback function

## -description

The PFND3DKMT_SETFSEBLOCK callback function sets FSE block.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETFSEBLOCK Pfnd3dkmtSetfseblock; 

// Definition

NTSTATUS Pfnd3dkmtSetfseblock 
(
	const D3DKMT_SETFSEBLOCK *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETFSEBLOCK](ns-d3dkmthk-_d3dkmt_setfseblock.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
