---
UID: NF:ntintsafe.RtlLongLongToUInt8
title: RtlLongLongToUInt8 function (ntintsafe.h)
description: Converts a value of type LONGLONG to a value of type UNIT8.
old-location: kernel\rtllonglongtouint8.htm
tech.root: kernel
ms.assetid: F0B69656-99DB-4FE1-BD39-3CE3F2676684
ms.date: 04/30/2018
keywords: ["RtlLongLongToUInt8 function"]
ms.keywords: RtlLongLongToUInt8, RtlLongLongToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtllonglongtouint8, ntintsafe/RtlLongLongToUInt8
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
 - RtlLongLongToUInt8
 - ntintsafe/RtlLongLongToUInt8
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlLongLongToUInt8
---

# RtlLongLongToUInt8 function


## -description

Converts a value of type <b>LONGLONG</b> to a value of type <b>UNIT8</b>.

## -parameters

### -param llOperand 

[in]
The value to be converted.

### -param pu8Result 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongLongToByte
</li>
<li>RtlLong64ToUInt8
</li>
<li>RtlLong64ToByte
</li>
<li>RtlInt64ToUInt8
</li>
<li>RtlInt64ToByte
</li>
</ul>

