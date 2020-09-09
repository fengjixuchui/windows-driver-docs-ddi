---
UID: NC:d3dkmthk.PFND3DKMT_QUERYFSEBLOCK
title: PFND3DKMT_QUERYFSEBLOCK (d3dkmthk.h)
description: The PFND3DKMT_QUERYFSEBLOCK callback function queries FSE blocks.
ms.assetid: 699577c3-0e0d-4518-88e7-40a6992a41ce
ms.date: 10/19/2018
keywords: ["PFND3DKMT_QUERYFSEBLOCK callback function"]
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
 - PFND3DKMT_QUERYFSEBLOCK
 - d3dkmthk/PFND3DKMT_QUERYFSEBLOCK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_QUERYFSEBLOCK
dev_langs:
 - c++
---

# PFND3DKMT_QUERYFSEBLOCK callback function


## -description

The PFND3DKMT_QUERYFSEBLOCK callback function queries FSE blocks.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_QUERYFSEBLOCK](ns-d3dkmthk-_d3dkmt_queryfseblock.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_QUERYFSEBLOCK Pfnd3dkmtQueryfseblock; 

// Definition

NTSTATUS Pfnd3dkmtQueryfseblock 
(
	D3DKMT_QUERYFSEBLOCK *
)
{...}

```

## -remarks

## -see-also

