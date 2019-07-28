---
UID: NF:ntintsafe.RtlUIntPtrToUInt
title: RtlUIntPtrToUInt function (ntintsafe.h)
description: Converts a value of type UINT_PTR to a value of type UINT.
old-location: kernel\rtluintptrtouint.htm
tech.root: kernel
ms.assetid: DA00BB09-7559-439A-935C-55A1304C6BBC
ms.date: 04/30/2018
ms.keywords: RtlUIntPtrToUInt, RtlUIntPtrToUInt function [Kernel-Mode Driver Architecture], kernel.rtluintptrtouint, ntintsafe/RtlUIntPtrToUInt
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlUIntPtrToUInt"
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
- RtlUIntPtrToUInt
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUIntPtrToUInt function


## -description


Converts a value of type <b>UINT_PTR</b> to a value of type <b>UINT</b>.


## -parameters




### -param uOperand

<p>The value to be converted.</p>


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrToUInt32
</li>
<li>RtlSizeTToUInt
</li>
<li>RtlSizeTToUInt32
</li>
</ul>


