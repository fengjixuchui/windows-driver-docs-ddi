---
UID: NF:ntintsafe.RtlUIntToInt
title: RtlUIntToInt function (ntintsafe.h)
description: Converts a value of type UINT to a value of type INT.
old-location: kernel\rtluinttoint.htm
tech.root: kernel
ms.assetid: 5C595F39-3F47-4B4D-B6C6-6CBC5848AA4B
ms.date: 04/30/2018
keywords: ["RtlUIntToInt function"]
ms.keywords: RtlUIntToInt, RtlUIntToInt function [Kernel-Mode Driver Architecture], kernel.rtluinttoint, ntintsafe/RtlUIntToInt
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
 - RtlUIntToInt
 - ntintsafe/RtlUIntToInt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlUIntToInt
---

# RtlUIntToInt function


## -description

Converts a value of type <b>UINT</b> to a value of type <b>INT</b>.

## -parameters

### -param uOperand 

[in]
The value to be converted.

### -param piResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

