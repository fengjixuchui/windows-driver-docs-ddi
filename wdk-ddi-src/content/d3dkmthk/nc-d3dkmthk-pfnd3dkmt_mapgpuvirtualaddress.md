---
UID: NC:d3dkmthk.PFND3DKMT_MAPGPUVIRTUALADDRESS
title: PFND3DKMT_MAPGPUVIRTUALADDRESS (d3dkmthk.h)
description: Pfnd3dkmtMapgpuvirtualaddress maps a graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the Invalid or Zero state.
ms.assetid: 261e50b0-8a71-4f06-84d5-b5601c469aac
ms.date: 10/19/2018
keywords: ["PFND3DKMT_MAPGPUVIRTUALADDRESS callback function"]
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
 - PFND3DKMT_MAPGPUVIRTUALADDRESS
 - d3dkmthk/PFND3DKMT_MAPGPUVIRTUALADDRESS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_MAPGPUVIRTUALADDRESS
dev_langs:
 - c++
---

# PFND3DKMT_MAPGPUVIRTUALADDRESS callback function


## -description

Pfnd3dkmtMapgpuvirtualaddress maps a graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the Invalid or Zero state.

## -parameters

### -param Arg1

Pointer to a [D3DDDI_MAPGPUVIRTUALADDRESS](../d3dukmdt/ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_MAPGPUVIRTUALADDRESS Pfnd3dkmtMapgpuvirtualaddress; 

// Definition

NTSTATUS Pfnd3dkmtMapgpuvirtualaddress 
(
	D3DDDI_MAPGPUVIRTUALADDRESS *
)
{...}

```

## -remarks

## -see-also

