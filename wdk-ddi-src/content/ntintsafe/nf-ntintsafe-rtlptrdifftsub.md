---
UID: NF:ntintsafe.RtlPtrdiffTSub
title: RtlPtrdiffTSub function (ntintsafe.h)
description: Subtracts one value of type PTRDIFF_T from another.
old-location: kernel\rtlptrdifftsub.htm
tech.root: kernel
ms.assetid: C87E3BD5-8CA7-443E-8CC3-F863CD4F321A
ms.date: 04/30/2018
keywords: ["RtlPtrdiffTSub function"]
ms.keywords: RtlPtrdiffTSub, RtlPtrdiffTSub function [Kernel-Mode Driver Architecture], kernel.rtlptrdifftsub, ntintsafe/RtlPtrdiffTSub
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
 - RtlPtrdiffTSub
 - ntintsafe/RtlPtrdiffTSub
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlPtrdiffTSub
---

# RtlPtrdiffTSub function


## -description

Subtracts one value of type <b>PTRDIFF_T</b> from another.

## -parameters

### -param Minuend 

[in]
The value from which <i>Subtrahend</i> is subtracted.

### -param Subtrahend 

[in]
The value to subtract from <i>Minuend</i>.

### -param pResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

