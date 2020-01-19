---
UID: NC:d3dkmddi.DXGKCB_ACQUIREHANDLEDATA
title: DXGKCB_ACQUIREHANDLEDATA (d3dkmddi.h)
description: Acquires a resource handle.
ms.assetid: e4ac45bd-29c0-4114-a68c-a43978c37b89
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DXGKCB_ACQUIREHANDLEDATA"
req.header: d3dkmddi.h
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
- d3dkmddi.h
api_name: 
- DXGKCB_ACQUIREHANDLEDATA
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: RS5
tech.root: display
---

# DXGKCB_ACQUIREHANDLEDATA callback function

## -description

Implemented by the client driver to acquire a resource handle. 

## -prototype

```cpp
//Declaration

DXGKCB_ACQUIREHANDLEDATA DxgkcbAcquirehandledata; 

// Definition

VOID * DxgkcbAcquirehandledata 
(
)
{...}

```

## -returns

Returns VOID.
