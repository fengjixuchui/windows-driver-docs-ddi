---
UID: NF:ntintsafe.RtlIntToShort
title: RtlIntToShort function (ntintsafe.h)
description: Converts a value of type INT to a value of type SHORT.
old-location: kernel\rtlinttoshort.htm
tech.root: kernel
ms.assetid: E8E05F9B-2F83-4537-979E-024E8412D733
ms.date: 04/30/2018
keywords: ["RtlIntToShort function"]
ms.keywords: RtlIntToShort, RtlIntToShort function [Kernel-Mode Driver Architecture], kernel.rtlinttoshort, ntintsafe/RtlIntToShort
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
 - RtlIntToShort
 - ntintsafe/RtlIntToShort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlIntToShort
---

# RtlIntToShort function


## -description

Converts a value of type <b>INT</b> to a value of type <b>SHORT</b>.

## -parameters

### -param iOperand 

[in]
The value to be converted.

### -param psResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntToInt16
</li>
<li>RtlInt32ToShort
</li>
<li>RtlInt32ToInt16
</li>
</ul>

