---
UID: NF:ntintsafe.RtlIntToULong
title: RtlIntToULong function (ntintsafe.h)
description: Converts a value of type INT to a value of type ULONG.
old-location: kernel\rtlinttoulong.htm
tech.root: kernel
ms.assetid: B5308AB1-3BF6-4B93-AC6B-655D00DFC5E5
ms.date: 04/30/2018
keywords: ["RtlIntToULong function"]
ms.keywords: RtlIntToULong, RtlIntToULong function [Kernel-Mode Driver Architecture], kernel.rtlinttoulong, ntintsafe/RtlIntToULong
f1_keywords:
 - "ntintsafe/RtlIntToULong"
 - "RtlIntToULong"
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
- RtlIntToULong
targetos: Windows
req.typenames: 
---

# RtlIntToULong function


## -description


Converts a value of type <b>INT</b> to a value of type <b>ULONG</b>.


## -parameters




### -param iOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntToULongPtr
</li>
<li>RtlIntToDWord
</li>
<li>RtlInt32ToULong
</li>
<li>RtlInt32ToDWord
</li>
<li>RtlIntToDWordPtr
</li>
<li>RtlIntToSIZET
</li>
<li>RtlInt32ToULongPtr
</li>
<li>RtlInt32ToDWordPtr
</li>
<li>RtlInt32ToSIZET
</li>
<li>RtlIntToULongPtr
</li>
</ul>


