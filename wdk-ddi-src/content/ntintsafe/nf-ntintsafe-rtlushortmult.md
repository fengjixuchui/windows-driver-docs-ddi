---
UID: NF:ntintsafe.RtlUShortMult
title: RtlUShortMult function (ntintsafe.h)
description: Multiplies one value of type USHORT by another.
old-location: kernel\rtlushortmult.htm
tech.root: kernel
ms.assetid: 1727AD96-FC0B-4B52-92C5-5E7502433021
ms.date: 04/30/2018
keywords: ["RtlUShortMult function"]
ms.keywords: RtlUShortMult, RtlUShortMult function [Kernel-Mode Driver Architecture], kernel.rtlushortmult, ntintsafe/RtlUShortMult
f1_keywords:
 - "ntintsafe/RtlUShortMult"
 - "RtlUShortMult"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntintsafe.h
api_name:
- RtlUShortMult
targetos: Windows
req.typenames: 
---

# RtlUShortMult function


## -description


Multiplies one value of type <b>USHORT</b> by another.


## -parameters




### -param usMultiplicand [in]

The value to be multiplied by <i>usMultiplier</i>.


### -param usMultiplier [in]

The value by which to multiply <i>usMultiplicand</i>.


### -param pusResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



