---
UID: NF:ntintsafe.RtlULongPtrToLongPtr
title: RtlULongPtrToLongPtr function (ntintsafe.h)
description: Converts a value of type ULONG_PTR to a value of type LONG_PTR.
old-location: kernel\rtlulongptrtolongptr.htm
tech.root: kernel
ms.assetid: 5231A8BC-2F7A-4A2C-931C-D3A81563754A
ms.date: 04/30/2018
keywords: ["RtlULongPtrToLongPtr function"]
ms.keywords: RtlULongPtrToLongPtr, RtlULongPtrToLongPtr function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtolongptr, ntintsafe/RtlULongPtrToLongPtr
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlULongPtrToLongPtr
 - ntintsafe/RtlULongPtrToLongPtr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlULongPtrToLongPtr
---

# RtlULongPtrToLongPtr function


## -description

Converts a value of type <b>ULONG_PTR</b> to a value of type <b>LONG_PTR</b>.

## -parameters

### -param ulOperand 

[in]
The value to be converted.

### -param plResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

