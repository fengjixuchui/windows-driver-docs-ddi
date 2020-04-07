---
UID: NF:ntintsafe.RtlLongToIntPtr
title: RtlLongToIntPtr function (ntintsafe.h)
description: Converts a value of type LONG to a value of type INT_PTR.
old-location: kernel\rtllongtointptr.htm
tech.root: kernel
ms.assetid: E583418C-7A23-4F88-A3D2-E2BA11578079
ms.date: 04/30/2018
keywords: ["RtlLongToIntPtr function"]
ms.keywords: RtlLongToIntPtr, RtlLongToIntPtr function [Kernel-Mode Driver Architecture], kernel.rtllongtointptr, ntintsafe/RtlLongToIntPtr
f1_keywords:
 - "ntintsafe/RtlLongToIntPtr"
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
- RtlLongToIntPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongToIntPtr function


## -description


Converts a value of type <b>LONG</b> to a value of type <b>INT_PTR</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToPtrdiffT</li>
</ul>


