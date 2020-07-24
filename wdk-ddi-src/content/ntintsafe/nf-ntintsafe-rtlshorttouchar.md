---
UID: NF:ntintsafe.RtlShortToUChar
title: RtlShortToUChar function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type UCHAR.
old-location: kernel\rtlshorttouchar.htm
tech.root: kernel
ms.assetid: 6DA0F939-F4B3-4E66-A90C-5112AE6FEC8D
ms.date: 04/30/2018
keywords: ["RtlShortToUChar function"]
ms.keywords: RtlShortToUChar, RtlShortToUChar function [Kernel-Mode Driver Architecture], kernel.rtlshorttouchar, ntintsafe/RtlShortToUChar
f1_keywords:
 - "ntintsafe/RtlShortToUChar"
 - "RtlShortToUChar"
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
- RtlShortToUChar
targetos: Windows
req.typenames: 
---

# RtlShortToUChar function


## -description


Converts a value of type <b>SHORT</b> to a value of type <b>UCHAR</b>.


## -parameters




### -param sOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt16ToUChar
</li>
</ul>


