---
UID: NF:ntintsafe.RtlUShortToUChar
title: RtlUShortToUChar function (ntintsafe.h)
description: Converts a value of type USHORT to a value of type UCHAR.
old-location: kernel\rtlushorttouchar.htm
tech.root: kernel
ms.assetid: E288541F-9FE4-4CF6-A576-21620A828C5C
ms.date: 04/30/2018
keywords: ["RtlUShortToUChar function"]
ms.keywords: RtlUShortToUChar, RtlUShortToUChar function [Kernel-Mode Driver Architecture], kernel.rtlushorttouchar, ntintsafe/RtlUShortToUChar
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
 - RtlUShortToUChar
 - ntintsafe/RtlUShortToUChar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlUShortToUChar
---

# RtlUShortToUChar function


## -description

Converts a value of type <b>USHORT</b> to a value of type <b>UCHAR</b>.

## -parameters

### -param usOperand 

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

