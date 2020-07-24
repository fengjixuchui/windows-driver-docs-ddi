---
UID: NC:d3dkmthk.PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
title: PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU (d3dkmthk.h)
description: The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU callback function enables a driver to signal a monitored fence.
ms.assetid: dd418f01-37ec-4972-a31b-eeb2d08a5b2f
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU"
 - "PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU"
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
- PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU callback function

## -description

The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU callback function enables a driver to signal a monitored fence.

## -prototype

```cpp
//Declaration

PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU Pfnd3dkmtSignalsynchronizationobjectfromcpu; 

// Definition

NTSTATUS Pfnd3dkmtSignalsynchronizationobjectfromcpu 
(
	const D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromcpu.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
