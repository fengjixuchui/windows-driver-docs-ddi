---
UID: NF:ntintsafe.RtlIntAdd
title: RtlIntAdd function (ntintsafe.h)
description: Adds two values of type INT.
old-location: kernel\rtlintadd.htm
tech.root: kernel
ms.assetid: DF556961-D5BA-4A50-9E6A-DACE96D13B50
ms.date: 04/30/2018
keywords: ["RtlIntAdd function"]
ms.keywords: RtlIntAdd, RtlIntAdd function [Kernel-Mode Driver Architecture], kernel.rtlintadd, ntintsafe/RtlIntAdd
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
 - RtlIntAdd
 - ntintsafe/RtlIntAdd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlIntAdd
---

# RtlIntAdd function


## -description

Adds two values of type <b>INT</b>.

## -parameters

### -param iAugend 

[in]
The first value in the equation.

### -param iAddend 

[in]
The value to add to <i>iAugend</i>.

### -param piResult 

[out]
A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt32Add
</li>
<li>RtlLong32Add
</li>
</ul>

