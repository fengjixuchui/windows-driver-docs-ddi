---
UID: NC:d3dkmthk.PFND3DKMT_QUERYRESOURCEINFO
title: PFND3DKMT_QUERYRESOURCEINFO (d3dkmthk.h)
description: The PFND3DKMT_QUERYRESOURCEINFO callback function retrieves information about a shared resource.
ms.assetid: 4e48ccbd-d20b-433f-aa1d-9c44fc5d930a
ms.date: 10/19/2018
keywords: ["PFND3DKMT_QUERYRESOURCEINFO callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_QUERYRESOURCEINFO"
 - "PFND3DKMT_QUERYRESOURCEINFO"
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
- PFND3DKMT_QUERYRESOURCEINFO
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_QUERYRESOURCEINFO callback function

## -description

The PFND3DKMT_QUERYRESOURCEINFO callback function retrieves information about a shared resource.

## -prototype

```cpp
//Declaration

PFND3DKMT_QUERYRESOURCEINFO Pfnd3dkmtQueryresourceinfo; 

// Definition

NTSTATUS Pfnd3dkmtQueryresourceinfo 
(
	D3DKMT_QUERYRESOURCEINFO *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_QUERYRESOURCEINFO](ns-d3dkmthk-_d3dkmt_queryresourceinfo.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
