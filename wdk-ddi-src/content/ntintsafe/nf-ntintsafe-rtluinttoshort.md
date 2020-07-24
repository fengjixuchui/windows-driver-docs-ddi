---
UID: NF:ntintsafe.RtlUIntToShort
title: RtlUIntToShort function (ntintsafe.h)
description: Converts a value of type UINT to a value of type SHORT.
old-location: kernel\rtluinttoshort.htm
tech.root: kernel
ms.assetid: 5D86CFF4-4943-475A-856E-3A97FE9C3E8A
ms.date: 04/30/2018
keywords: ["RtlUIntToShort function"]
ms.keywords: RtlUIntToShort, RtlUIntToShort function [Kernel-Mode Driver Architecture], kernel.rtluinttoshort, ntintsafe/RtlUIntToShort
f1_keywords:
 - "ntintsafe/RtlUIntToShort"
 - "RtlUIntToShort"
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
- RtlUIntToShort
targetos: Windows
req.typenames: 
---

# RtlUIntToShort function


## -description


Converts a value of type <b>UINT</b> to a value of type <b>SHORT</b>.


## -parameters




### -param uOperand [in]

The value to be converted.


### -param psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntToInt16
</li>
<li>RtlUInt32ToShort
</li>
<li>RtlUInt32ToInt16
</li>
</ul>


