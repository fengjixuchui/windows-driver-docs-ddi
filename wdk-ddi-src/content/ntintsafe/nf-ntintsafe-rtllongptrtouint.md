---
UID: NF:ntintsafe.RtlLongPtrToUInt
title: RtlLongPtrToUInt function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type UINT.
old-location: kernel\rtllongptrtouint.htm
tech.root: kernel
ms.assetid: BE22A848-1A3B-45A7-815D-F7A389A81651
ms.date: 04/30/2018
keywords: ["RtlLongPtrToUInt function"]
ms.keywords: RtlLongPtrToUInt, RtlLongPtrToUInt function [Kernel-Mode Driver Architecture], kernel.rtllongptrtouint, ntintsafe/RtlLongPtrToUInt
f1_keywords:
 - "ntintsafe/RtlLongPtrToUInt"
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
- RtlLongPtrToUInt
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongPtrToUInt function


## -description


Converts a value of type <b>LONG_PTR</b> to a value of type <b>UINT</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongPtrToUInt32
</li>
<li>RtlSSIZETToUInt
</li>
<li>RtlSSIZETToUInt32
</li>
</ul>


