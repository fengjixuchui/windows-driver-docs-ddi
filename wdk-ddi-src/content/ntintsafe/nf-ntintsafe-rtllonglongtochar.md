---
UID: NF:ntintsafe.RtlLongLongToChar
title: RtlLongLongToChar function (ntintsafe.h)
description: Converts a value of type LONGLONG to a value of type CHAR.
old-location: kernel\rtllonglongtochar.htm
tech.root: kernel
ms.assetid: E69889FC-11EF-4C49-A550-7C9C9FE1FDA7
ms.date: 04/30/2018
keywords: ["RtlLongLongToChar function"]
ms.keywords: RtlLongLongToChar, RtlLongLongToChar function [Kernel-Mode Driver Architecture], kernel.rtllonglongtochar, ntintsafe/RtlLongLongToChar
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
 - RtlLongLongToChar
 - ntintsafe/RtlLongLongToChar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongLongToChar
---

# RtlLongLongToChar function


## -description

Converts a value of type <b>LONGLONG</b> to a value of type <b>CHAR</b>.

## -parameters

### -param llOperand 

[in]
The value to be converted.

### -param pch 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLong64ToChar
</li>
<li>RtlInt64ToChar
</li>
</ul>

