---
UID: NF:ntintsafe.RtlULongLongAdd
title: RtlULongLongAdd function (ntintsafe.h)
description: Adds two values of type ULONGLONG.
old-location: kernel\rtlulonglongadd.htm
tech.root: kernel
ms.assetid: AE58D20E-25A0-4D45-9E60-38EF2F1D1EF3
ms.date: 04/30/2018
keywords: ["RtlULongLongAdd function"]
ms.keywords: RtlULongLongAdd, RtlULongLongAdd function [Kernel-Mode Driver Architecture], kernel.rtlulonglongadd, ntintsafe/RtlULongLongAdd
f1_keywords:
 - "ntintsafe/RtlULongLongAdd"
 - "RtlULongLongAdd"
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
- RtlULongLongAdd
targetos: Windows
req.typenames: 
---

# RtlULongLongAdd function


## -description


Adds two values of type <b>ULONGLONG</b>.


## -parameters




### -param ullAugend [in]

The first value in the equation.


### -param ullAddend [in]

The value to add to <i>ullAugend</i>.


### -param pullResult

<p>A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>




## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



