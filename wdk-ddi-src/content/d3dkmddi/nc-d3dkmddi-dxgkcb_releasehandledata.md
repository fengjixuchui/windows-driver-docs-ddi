---
UID: NC:d3dkmddi.DXGKCB_RELEASEHANDLEDATA
title: DXGKCB_RELEASEHANDLEDATA (d3dkmddi.h)
description: Releases handle data.
ms.assetid: b7a1b8b8-f631-478b-a441-c89dcd7bfd29
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DXGKCB_RELEASEHANDLEDATA"
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
- DXGKCB_RELEASEHANDLEDATA
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# DXGKCB_RELEASEHANDLEDATA callback function

## -description

Implemented by the client driver to release handle data.

## -prototype

```cpp
//Declaration

DXGKCB_RELEASEHANDLEDATA DxgkcbReleasehandledata; 

// Definition

VOID DxgkcbReleasehandledata 
(
)
{...}

```

## -parameters




## -returns

Returns VOID.
