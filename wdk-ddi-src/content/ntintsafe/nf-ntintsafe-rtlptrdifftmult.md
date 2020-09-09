---
UID: NF:ntintsafe.RtlPtrdiffTMult
title: RtlPtrdiffTMult function (ntintsafe.h)
description: Multiplies one value of type PTRDIFF_T by another.
old-location: kernel\rtlptrdifftmult.htm
tech.root: kernel
ms.assetid: 71F6D886-D32E-4C90-B5BA-A4A1BBCD0B8F
ms.date: 04/30/2018
keywords: ["RtlPtrdiffTMult function"]
ms.keywords: RtlPtrdiffTMult, RtlPtrdiffTMult function [Kernel-Mode Driver Architecture], kernel.rtlptrdifftmult, ntintsafe/RtlPtrdiffTMult
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
 - RtlPtrdiffTMult
 - ntintsafe/RtlPtrdiffTMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlPtrdiffTMult
---

# RtlPtrdiffTMult function


## -description

Multiplies one value of type <b>PTRDIFF_T</b> by another.

## -parameters

### -param Multiplicand 

[in]
The value to be multiplied by <i>Multiplier</i>.

### -param Multiplier 

[in]
The value by which to multiply <i>Multiplicand</i>.

### -param pResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

