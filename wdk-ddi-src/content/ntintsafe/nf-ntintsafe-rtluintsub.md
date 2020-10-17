---
UID: NF:ntintsafe.RtlUIntSub
title: RtlUIntSub function (ntintsafe.h)
description: Subtracts one value of type UINT from another.
old-location: kernel\rtluintsub.htm
tech.root: kernel
ms.assetid: 0886578A-C1CF-4A48-86A3-407A0C16ADEC
ms.date: 04/30/2018
keywords: ["RtlUIntSub function"]
ms.keywords: RtlUIntSub, RtlUIntSub function [Kernel-Mode Driver Architecture], kernel.rtluintsub, ntintsafe/RtlUIntSub
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
 - RtlUIntSub
 - ntintsafe/RtlUIntSub
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlUIntSub
---

# RtlUIntSub function


## -description

Subtracts one value of type <b>UINT</b> from another.

## -parameters

### -param uMinuend 

[in]
The value from which <i>u8Subtrahend</i> is subtracted.

### -param uSubtrahend 

[in]
The value to subtract from <i>u8Minuend</i>.

### -param puResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUInt32Sub
</li>
</ul>

