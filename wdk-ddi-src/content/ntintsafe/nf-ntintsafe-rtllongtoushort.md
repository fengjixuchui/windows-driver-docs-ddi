---
UID: NF:ntintsafe.RtlLongToUShort
title: RtlLongToUShort function (ntintsafe.h)
description: Converts a value of type LONG to a value of type USHORT.
old-location: kernel\rtllongtoushort.htm
tech.root: kernel
ms.assetid: A6D3E5D2-EB53-4F1D-B4E4-9E2D8D845E80
ms.date: 04/30/2018
keywords: ["RtlLongToUShort function"]
ms.keywords: RtlLongToUShort, RtlLongToUShort function [Kernel-Mode Driver Architecture], kernel.rtllongtoushort, ntintsafe/RtlLongToUShort
f1_keywords:
 - "ntintsafe/RtlLongToUShort"
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
- RtlLongToUShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongToUShort function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>USHORT</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pusResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToUInt16
</li>
<li>RtlLongToWord
</li>
</ul>


