---
UID: NF:ntintsafe.RtlInt8ToUInt
title: RtlInt8ToUInt function (ntintsafe.h)
description: Converts a value of type INT8 to a value of type UINT.
old-location: kernel\rtlint8touint.htm
tech.root: kernel
ms.assetid: 00C37CB5-4CBC-48C3-8D90-F01BF82E2EF6
ms.date: 04/30/2018
keywords: ["RtlInt8ToUInt function"]
ms.keywords: RtlInt8ToUInt, RtlInt8ToUInt function [Kernel-Mode Driver Architecture], kernel.rtlint8touint, ntintsafe/RtlInt8ToUInt
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
 - RtlInt8ToUInt
 - ntintsafe/RtlInt8ToUInt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlInt8ToUInt
---

# RtlInt8ToUInt function


## -description

Converts a value of type <b>INT8</b> to a value of type <b>UINT</b>.

## -parameters

### -param i8Operand 

[in]
The value to be converted.

### -param puResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt8ToUInt32
</li>
</ul>

