---
UID: NF:ntintsafe.RtlLongLongAdd
title: RtlLongLongAdd function (ntintsafe.h)
description: Adds two values of type LONGLONG.
old-location: kernel\rtllonglongadd.htm
tech.root: kernel
ms.assetid: 94FD1DD3-0799-4E90-A115-9EF065433B05
ms.date: 04/30/2018
keywords: ["RtlLongLongAdd function"]
ms.keywords: RtlLongLongAdd, RtlLongLongAdd function [Kernel-Mode Driver Architecture], kernel.rtllonglongadd, ntintsafe/RtlLongLongAdd
f1_keywords:
 - "ntintsafe/RtlLongLongAdd"
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
- RtlLongLongAdd
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongLongAdd function


## -description


Adds two values of type <b>LONGLONG</b>.


## -parameters




### -param llAugend [in]

The first value in the equation.


### -param llAddend [in]

The value to add to <i>llAugend</i>.


### -param pllResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrAdd
</li>
<li>RtlLongPtrAdd
</li>
<li>RtlLong64Add
</li>
<li>RtlInt64Add
</li>
<li>RtlPtrdiffTAdd
</li>
<li>RtlSSIZETAdd
</li>
</ul>


