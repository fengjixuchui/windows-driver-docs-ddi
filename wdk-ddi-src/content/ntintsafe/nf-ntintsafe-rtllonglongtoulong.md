---
UID: NF:ntintsafe.RtlLongLongToULong
title: RtlLongLongToULong function (ntintsafe.h)
description: Converts a value of type LONGLONG to a value of type ULONG.
old-location: kernel\rtllonglongtoulong.htm
tech.root: kernel
ms.assetid: EA5C57D3-E4EF-49B2-9B0E-DB99CD32C888
ms.date: 04/30/2018
ms.keywords: RtlLongLongToULong, RtlLongLongToULong function [Kernel-Mode Driver Architecture], kernel.rtllonglongtoulong, ntintsafe/RtlLongLongToULong
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlLongLongToULong"
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
- RtlLongLongToULong
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongLongToULong function


## -description


Converts a value of type <b>LONGLONG</b> to a value of type <b>ULONG</b>.


## -parameters




### -param llOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlIntPtrToULong
</li>
<li>RtlLongPtrToULong
</li>
<li>RtlLongLongToULongPtr
</li>
<li>RtlLongLongToDWord
</li>
<li>RtlLong64ToULong
</li>
<li>RtlLong64ToDWord
</li>
<li>RtlInt64ToULong
</li>
<li>RtlInt64ToDWord
</li>
</ul>


