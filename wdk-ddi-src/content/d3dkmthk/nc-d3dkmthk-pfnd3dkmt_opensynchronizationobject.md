---
UID: NC:d3dkmthk.PFND3DKMT_OPENSYNCHRONIZATIONOBJECT
title: PFND3DKMT_OPENSYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The PFND3DKMT_OPENSYNCHRONIZATIONOBJECT callback function opens a kernel-mode synchronization object.
ms.assetid: 8a699ba7-c32a-4670-84ca-a5c896455d82
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OPENSYNCHRONIZATIONOBJECT callback function"]
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
 - PFND3DKMT_OPENSYNCHRONIZATIONOBJECT
 - d3dkmthk/PFND3DKMT_OPENSYNCHRONIZATIONOBJECT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_OPENSYNCHRONIZATIONOBJECT
dev_langs:
 - c++
---

# PFND3DKMT_OPENSYNCHRONIZATIONOBJECT callback function


## -description

The PFND3DKMT_OPENSYNCHRONIZATIONOBJECT callback function opens a kernel-mode synchronization object.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_OPENSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_opensynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENSYNCHRONIZATIONOBJECT Pfnd3dkmtOpensynchronizationobject; 

// Definition

NTSTATUS Pfnd3dkmtOpensynchronizationobject 
(
	D3DKMT_OPENSYNCHRONIZATIONOBJECT *
)
{...}

```

## -remarks

## -see-also

