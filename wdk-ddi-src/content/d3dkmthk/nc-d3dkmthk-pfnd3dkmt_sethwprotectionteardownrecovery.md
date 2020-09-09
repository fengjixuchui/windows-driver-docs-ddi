---
UID: NC:d3dkmthk.PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY
title: PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY (d3dkmthk.h)
description: The PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY callback function sets the hardware protection tear down recovery.
ms.assetid: 7beb2a30-1171-4ad3-8ae3-8358e55921a0
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY callback function"]
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
 - PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY
 - d3dkmthk/PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY
dev_langs:
 - c++
---

# PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY callback function


## -description

The PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY callback function sets the hardware protection tear down recovery.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY](ns-d3dkmthk-_d3dkmt_sethwprotectionteardownrecovery.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY Pfnd3dkmtSethwprotectionteardownrecovery; 

// Definition

NTSTATUS Pfnd3dkmtSethwprotectionteardownrecovery 
(
	D3DKMT_SETHWPROTECTIONTEARDOWNRECOVERY *
)
{...}

```

## -remarks

## -see-also

