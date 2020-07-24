---
UID: NF:ntintsafe.RtlDWordPtrSub
title: RtlDWordPtrSub function (ntintsafe.h)
description: Subtracts one value of type DWORD_PTR from another.
old-location: kernel\rtldwordptrsub.htm
tech.root: kernel
ms.assetid: B3268640-F256-4B64-AE95-8D30A6A7BF6C
ms.date: 04/30/2018
keywords: ["RtlDWordPtrSub function"]
ms.keywords: RtlDWordPtrSub, RtlDWordPtrSub function [Kernel-Mode Driver Architecture], kernel.rtldwordptrsub, ntintsafe/RtlDWordPtrSub
f1_keywords:
 - "ntintsafe/RtlDWordPtrSub"
 - "RtlDWordPtrSub"
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
- RtlDWordPtrSub
targetos: Windows
req.typenames: 
---

# RtlDWordPtrSub function


## -description


Subtracts one value of type <b>DWORD_PTR</b> from another.


## -parameters




### -param dwMinuend [in]

The value from which <i>dwSubtrahend</i> is subtracted.


### -param dwSubtrahend [in]

The value to subtract from <i>dwMinuend</i>.


### -param pdwResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



