---
UID: NF:ntintsafe.RtlUShortToChar
title: RtlUShortToChar function (ntintsafe.h)
description: Converts a value of type USHORT to a value of type CHAR.
old-location: kernel\rtlushorttochar.htm
tech.root: kernel
ms.assetid: 13C5988F-1669-4B18-9423-74587276320F
ms.date: 04/30/2018
keywords: ["RtlUShortToChar function"]
ms.keywords: RtlUShortToChar, RtlUShortToChar function [Kernel-Mode Driver Architecture], kernel.rtlushorttochar, ntintsafe/RtlUShortToChar
f1_keywords:
 - "ntintsafe/RtlUShortToChar"
 - "RtlUShortToChar"
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
- RtlUShortToChar
targetos: Windows
req.typenames: 
---

# RtlUShortToChar function


## -description


Converts a value of type <b>USHORT</b> to a value of type <b>CHAR</b>.


## -parameters




### -param usOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



