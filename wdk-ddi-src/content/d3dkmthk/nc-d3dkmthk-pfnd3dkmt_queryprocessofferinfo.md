---
UID: NC:d3dkmthk.PFND3DKMT_QUERYPROCESSOFFERINFO
title: PFND3DKMT_QUERYPROCESSOFFERINFO (d3dkmthk.h)
description: The PFND3DKMT_QUERYPROCESSOFFERINFO callback function queries the process offer info.
ms.assetid: 607cf96a-6c35-4eab-adc4-1eb12f2c1eae
ms.date: 10/19/2018
keywords: ["PFND3DKMT_QUERYPROCESSOFFERINFO callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_QUERYPROCESSOFFERINFO"
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
- PFND3DKMT_QUERYPROCESSOFFERINFO
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_QUERYPROCESSOFFERINFO callback function

## -description

The PFND3DKMT_QUERYPROCESSOFFERINFO callback function queries the process offer info.

## -prototype

```cpp
//Declaration

PFND3DKMT_QUERYPROCESSOFFERINFO Pfnd3dkmtQueryprocessofferinfo; 

// Definition

NTSTATUS Pfnd3dkmtQueryprocessofferinfo 
(
	D3DKMT_QUERYPROCESSOFFERINFO *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_QUERYPROCESSOFFERINFO](ns-d3dkmthk-_d3dkmt_queryprocessofferinfo.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
