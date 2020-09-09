---
UID: NC:d3dumddi.PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB
title: PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB (d3dumddi.h)
description: Implemented by the client driver to submit a present blt to the hardware queue.
ms.assetid: e699bb81-9414-4396-a08b-11ae38b3d8c2
ms.date: 10/19/2018
keywords: ["PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB callback function"]
req.header: d3dumddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
tech.root: display
f1_keywords:
 - PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB
 - d3dumddi/PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB
product:
 - Windows
---

# PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB callback function


## -description

Implemented by the client driver to submit a present blt to the hardware queue.

## -parameters

### -param hDevice

A handle to the device.

### -param Arg2

A pointer to the [D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE](ns-d3dumddi-_d3dddicb_submitpresentblttohwqueue.md) structure that holds information on submitting a present blt to the hardware queue.

## -returns

|Return code|Description|
|--|--|
|S_OK|The call was completed successfully.|


This function might also return other HRESULT values.

## -prototype

```cpp
//Declaration

PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB Pfnd3dddiSubmitpresentblttohwqueuecb;

// Definition

HRESULT Pfnd3dddiSubmitpresentblttohwqueuecb
(
	HANDLE hDevice
	D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE *
)
{...}

PFND3DDDI_SUBMITPRESENTBLTTOHWQUEUECB


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DDDICB_SUBMITPRESENTBLTTOHWQUEUE](ns-d3dumddi-_d3dddicb_submitpresentblttohwqueue.md) and then calling Pfnd3dddiSubmitpresentblttohwqueuecb.

