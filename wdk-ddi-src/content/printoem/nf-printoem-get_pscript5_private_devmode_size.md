---
UID: NF:printoem.GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE
title: GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE macro (printoem.h)
description: 
ms.assetid: cda9100c-5b0f-4bf8-8d85-d920d23d8ceb
ms.date: 10/19/2018
keywords: ["GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE macro"]
f1_keywords:
 - "printoem/GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE"
 - "GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE"
ms.keywords: GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE
req.header: printoem.h
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
- HeaderDef
api_location: 
- printoem.h
api_name: 
- GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE macro

## -description

Returns PScript5's private DEVMODE structure to allow its plugins to determine its size.

## -parameters

### -param pdm

Contains the size of the private DEVMODE structure.

The macro is defined as follows:

```cpp
#define GET_PSCRIPT5_PRIVATE_DEVMODE_SIZE(pdm) \
    ( ( (pdm)->dmDriverExtra > (FIELD_OFFSET(PSCRIPT5_PRIVATE_DEVMODE, wSize) + sizeof(WORD)) ) ? \
        ((PPSCRIPT5_PRIVATE_DEVMODE)((PBYTE)(pdm) + (pdm)->dmSize))->wSize : 0 )
```

## -remarks

## -see-also
