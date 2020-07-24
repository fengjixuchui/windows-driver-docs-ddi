---
UID: NF:dbgmodel.Location.Location
title: Location function (dbgmodel.h)
description: Copy constructs a location.
ms.assetid: e50b6f55-a47e-4fbc-b7f1-041cbccf9ea5
ms.date: 09/28/2018
keywords: ["Location function"]
f1_keywords:
 - "dbgmodel/Location"
 - "Location"
ms.keywords: Location
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
- HeaderDef
api_location: 
- dbgmodel.h
api_name: 
- Location
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# Location function


## -description

Copy constructs a location.

Default constructs an equivalent nullptr.

## -returns
This function is a constructor and does not return value.

## -remarks
Defines the location for an object.  This particular variant of Location is the C-COM access struct.
Note that a location only has meaning in conjunction with a host context.  It is a location within
a context.  When performing an operation on the location (reading bytes, writing bytes, etc...), 
a valid host context must be supplied.

## -see-also
[dbgmodel.h header](https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgmodel/)

