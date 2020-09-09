---
UID: NF:ntintsafe.RtlLongMult
title: RtlLongMult function (ntintsafe.h)
description: Multiplies one value of type LONG by another.
old-location: kernel\rtllongmult.htm
tech.root: kernel
ms.assetid: A95A88B6-066F-4489-B5C0-B012E831D7AD
ms.date: 04/30/2018
keywords: ["RtlLongMult function"]
ms.keywords: RtlLongMult, RtlLongMult function [Kernel-Mode Driver Architecture], kernel.rtllongmult, ntintsafe/RtlLongMult
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
 - RtlLongMult
 - ntintsafe/RtlLongMult
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongMult
---

# RtlLongMult function


## -description

Multiplies one value of type <b>LONG</b> by another.

## -parameters

### -param lMultiplicand 

[in]
The value to be multiplied by <i>lMultiplier</i>.

### -param lMultiplier 

[in]
The value by which to multiply <i>lMultiplicand</i>.

### -param plResult 

[out]
A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

