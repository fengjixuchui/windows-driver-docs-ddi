---
UID: NF:ntintsafe.RtlShortToUInt
title: RtlShortToUInt function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type UINT.
old-location: kernel\rtlshorttouint.htm
tech.root: kernel
ms.assetid: D4651C81-7171-4D54-BB76-EE822AABC1C3
ms.date: 04/30/2018
keywords: ["RtlShortToUInt function"]
ms.keywords: RtlShortToUInt, RtlShortToUInt function [Kernel-Mode Driver Architecture], kernel.rtlshorttouint, ntintsafe/RtlShortToUInt
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
 - RtlShortToUInt
 - ntintsafe/RtlShortToUInt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlShortToUInt
---

# RtlShortToUInt function


## -description

Converts a value of type <b>SHORT</b> to a value of type <b>UINT</b>.

## -parameters

### -param sOperand 

[in]
The value to be converted.

### -param puResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlShortToUInt32
</li>
<li>RtlInt16ToUInt
</li>
<li>RtlInt16ToUInt32
</li>
</ul>

