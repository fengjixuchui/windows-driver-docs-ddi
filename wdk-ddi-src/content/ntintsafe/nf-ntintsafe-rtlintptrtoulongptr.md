---
UID: NF:ntintsafe.RtlIntPtrToULongPtr
title: RtlIntPtrToULongPtr function (ntintsafe.h)
description: Converts a value of type INT_PTR to a value of type ULONG_PTR.
old-location: kernel\rtlintptrtoulongptr.htm
tech.root: kernel
ms.assetid: DE6CD62F-0792-490A-9DDD-A979CAC0565A
ms.date: 04/30/2018
keywords: ["RtlIntPtrToULongPtr function"]
ms.keywords: RtlIntPtrToULongPtr, RtlIntPtrToULongPtr function [Kernel-Mode Driver Architecture], kernel.rtlintptrtoulongptr, ntintsafe/RtlIntPtrToULongPtr
f1_keywords:
 - "ntintsafe/RtlIntPtrToULongPtr"
 - "RtlIntPtrToULongPtr"
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
- RtlIntPtrToULongPtr
targetos: Windows
req.typenames: 
---

# RtlIntPtrToULongPtr function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>ULONG_PTR</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToDWordPtr
</li>
<li>RtlIntPtrToSIZET
</li>
<li>RtlPtrdiffTToULongPtr
</li>
<li>RtlPtrdiffTToDWordPtr
</li>
<li>RtlPtrdiffTToSIZET
</li>
</ul>


