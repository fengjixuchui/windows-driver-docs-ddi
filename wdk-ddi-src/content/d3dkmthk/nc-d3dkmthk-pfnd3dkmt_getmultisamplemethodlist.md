---
UID: NC:d3dkmthk.PFND3DKMT_GETMULTISAMPLEMETHODLIST
title: PFND3DKMT_GETMULTISAMPLEMETHODLIST (d3dkmthk.h)
description: Pfnd3dkmtGetmultisamplemethodlist retrieves a list of multiple-sample methods that are used for an allocation.
ms.assetid: a3421422-c620-44b7-8799-2115e8bbb6ac
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETMULTISAMPLEMETHODLIST callback function"]
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
 - PFND3DKMT_GETMULTISAMPLEMETHODLIST
 - d3dkmthk/PFND3DKMT_GETMULTISAMPLEMETHODLIST
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETMULTISAMPLEMETHODLIST
dev_langs:
 - c++
---

# PFND3DKMT_GETMULTISAMPLEMETHODLIST callback function


## -description

Pfnd3dkmtGetmultisamplemethodlist retrieves a list of multiple-sample methods that are used for an allocation.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_GETMULTISAMPLEMETHODLIST](ns-d3dkmthk-_d3dkmt_getmultisamplemethodlist.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETMULTISAMPLEMETHODLIST Pfnd3dkmtGetmultisamplemethodlist; 

// Definition

NTSTATUS Pfnd3dkmtGetmultisamplemethodlist 
(
	D3DKMT_GETMULTISAMPLEMETHODLIST *
)
{...}

```

## -remarks

## -see-also

