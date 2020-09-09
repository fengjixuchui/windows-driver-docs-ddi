---
UID: NC:d3dkmthk.PFND3DKMT_OPENADAPTERFROMLUID
title: PFND3DKMT_OPENADAPTERFROMLUID (d3dkmthk.h)
description: Pfnd3dkmtOpenadapterfromluid maps a locally unique identifier (LUID) to a graphics adapter handle.
ms.assetid: 14e613a4-3b9a-4c8c-aa87-c75ed773b7a1
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OPENADAPTERFROMLUID callback function"]
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
 - PFND3DKMT_OPENADAPTERFROMLUID
 - d3dkmthk/PFND3DKMT_OPENADAPTERFROMLUID
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_OPENADAPTERFROMLUID
dev_langs:
 - c++
---

# PFND3DKMT_OPENADAPTERFROMLUID callback function


## -description

Pfnd3dkmtOpenadapterfromluid maps a locally unique identifier (LUID) to a graphics adapter handle.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_OPENADAPTERFROMLUID](ns-d3dkmthk-_d3dkmt_openadapterfromluid.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENADAPTERFROMLUID Pfnd3dkmtOpenadapterfromluid; 

// Definition

NTSTATUS Pfnd3dkmtOpenadapterfromluid 
(
	D3DKMT_OPENADAPTERFROMLUID *
)
{...}

```

## -remarks

## -see-also

