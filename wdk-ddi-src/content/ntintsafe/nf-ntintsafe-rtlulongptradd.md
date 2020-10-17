---
UID: NF:ntintsafe.RtlULongPtrAdd
title: RtlULongPtrAdd function (ntintsafe.h)
description: Adds two values of type ULONG_PTR.
old-location: kernel\rtlulongptradd.htm
tech.root: kernel
ms.assetid: 26A9A0B6-07A3-4D42-A5A1-C4CDD541A3FA
ms.date: 04/30/2018
keywords: ["RtlULongPtrAdd function"]
ms.keywords: RtlULongPtrAdd, RtlULongPtrAdd function [Kernel-Mode Driver Architecture], kernel.rtlulongptradd, ntintsafe/RtlULongPtrAdd
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
 - RtlULongPtrAdd
 - ntintsafe/RtlULongPtrAdd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlULongPtrAdd
---

# RtlULongPtrAdd function


## -description

Adds two values of type <b>ULONG_PTR</b>.

## -parameters

### -param ulAugend 

[in]
The first value in the equation.

### -param ulAddend 

[in]
The value to add to <i>ulAugend</i>.

### -param pulResult 

[out]
A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 
