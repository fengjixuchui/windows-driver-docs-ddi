---
UID: NF:ntintsafe.RtlShortToChar
title: RtlShortToChar function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type CHAR.
old-location: kernel\rtlshorttochar.htm
tech.root: kernel
ms.assetid: AC7D5479-7C68-445A-9788-F5E96D6BB41E
ms.date: 04/30/2018
keywords: ["RtlShortToChar function"]
ms.keywords: RtlShortToChar, RtlShortToChar function [Kernel-Mode Driver Architecture], kernel.rtlshorttochar, ntintsafe/RtlShortToChar
f1_keywords:
 - "ntintsafe/RtlShortToChar"
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
- RtlShortToChar
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlShortToChar function


## -description


Converts a value of type <b>SHORT</b> to a value of type <b>CHAR</b>.


## -parameters




### -param sOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlInt16ToChar
</li>
</ul>


