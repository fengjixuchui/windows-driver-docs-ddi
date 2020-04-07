---
UID: NF:ntintsafe.RtlIntPtrToShort
title: RtlIntPtrToShort function (ntintsafe.h)
description: Converts a value of type INT_PTR to a value of type SHORT.
old-location: kernel\rtlintptrtoshort.htm
tech.root: kernel
ms.assetid: 658F4C4E-D8E4-4624-BDF1-314A5B15CF67
ms.date: 04/30/2018
keywords: ["RtlIntPtrToShort function"]
ms.keywords: RtlIntPtrToShort, RtlIntPtrToShort function [Kernel-Mode Driver Architecture], kernel.rtlintptrtoshort, ntintsafe/RtlIntPtrToShort
f1_keywords:
 - "ntintsafe/RtlIntPtrToShort"
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
- RtlIntPtrToShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntPtrToShort function


## -description


Converts a value of type <b>INT_PTR</b> to a value of type <b>SHORT</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntPtrToInt16
</li>
<li>RtlPtrdiffTToShort
</li>
<li>RtlPtrdiffTToInt16
</li>
</ul>


