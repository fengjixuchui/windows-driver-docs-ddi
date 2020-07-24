---
UID: NF:ntintsafe.RtlULongToUInt8
title: RtlULongToUInt8 function (ntintsafe.h)
description: Converts a value of type ULONG_PTR to a value of type UINT8.
old-location: kernel\rtlulongtouint8.htm
tech.root: kernel
ms.assetid: 56A205A5-A7A8-440D-B28B-B925E2107AEE
ms.date: 04/30/2018
keywords: ["RtlULongToUInt8 function"]
ms.keywords: RtlULongToUInt8, RtlULongToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtlulongtouint8, ntintsafe/RtlULongToUInt8
f1_keywords:
 - "ntintsafe/RtlULongToUInt8"
 - "RtlULongToUInt8"
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
- RtlULongToUInt8
targetos: Windows
req.typenames: 
---

# RtlULongToUInt8 function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>UINT8</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param pui8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



