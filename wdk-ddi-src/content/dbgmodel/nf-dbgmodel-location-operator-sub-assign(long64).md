---
UID: NF:dbgmodel.Location.operator-sub-assign(LONG64)
title: operator-= function (dbgmodel.h)
description: The subtraction assignment operator for the location function.
ms.assetid: 4f8fc5c4-580b-410d-bfed-5ecea0f05089
ms.date: 09/28/2018
keywords: ["operator-= function"]
f1_keywords:
 - "dbgmodel/operator-="
 - "operator-="
ms.keywords: operator-=
req.header: dbgmodel.h
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
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- operator-=
targetos: Windows
tech.root: debugger
---

# operator-= function

## -description
The subtraction assignment operator for the location function.

## -parameters

### -param offset
Subtracts this value from the location’s offset into its address space.  The location will then refer ‘offset’ bytes prior to where it previously did.

## -returns
This function returns Location &.

## -remarks

## -see-also

[dbgmodel.h header](./index.md)