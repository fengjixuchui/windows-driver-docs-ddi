---
UID: NC:d3dkmthk.PFND3DKMT_OPENSYNCHRONIZATIONOBJECT
title: PFND3DKMT_OPENSYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The PFND3DKMT_OPENSYNCHRONIZATIONOBJECT callback function opens a kernel-mode synchronization object.
ms.assetid: 8a699ba7-c32a-4670-84ca-a5c896455d82
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OPENSYNCHRONIZATIONOBJECT callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_OPENSYNCHRONIZATIONOBJECT"
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
- PFND3DKMT_OPENSYNCHRONIZATIONOBJECT
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_OPENSYNCHRONIZATIONOBJECT callback function

## -description

The PFND3DKMT_OPENSYNCHRONIZATIONOBJECT callback function opens a kernel-mode synchronization object.

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

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_opensynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
