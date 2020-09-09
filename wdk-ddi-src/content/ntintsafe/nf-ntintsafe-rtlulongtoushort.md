---
UID: NF:ntintsafe.RtlULongToUShort
title: RtlULongToUShort function (ntintsafe.h)
description: Converts a value of type ULONG to a value of type USHORT.
old-location: kernel\rtlulongtoushort.htm
tech.root: kernel
ms.assetid: 6D03736F-E972-4A76-935A-BB8682DC38B8
ms.date: 04/30/2018
keywords: ["RtlULongToUShort function"]
ms.keywords: RtlULongToUShort, RtlULongToUShort function [Kernel-Mode Driver Architecture], kernel.rtlulongtoushort, ntintsafe/RtlULongToUShort
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
 - RtlULongToUShort
 - ntintsafe/RtlULongToUShort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlULongToUShort
---

# RtlULongToUShort function


## -description

Converts a value of type <b>ULONG</b> to a value of type <b>USHORT</b>.

## -parameters

### -param ulOperand 

[in]
The value to be converted.

### -param pusResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

