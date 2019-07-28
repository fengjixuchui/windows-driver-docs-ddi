---
UID: NF:ntintsafe.RtlULongToUChar
title: RtlULongToUChar function (ntintsafe.h)
description: Converts a value of type ULONG to a value of type UCHAR.
old-location: kernel\rtlulongtouchar.htm
tech.root: kernel
ms.assetid: 4958FB4E-D049-40EB-A6CA-973DCF7F397B
ms.date: 04/30/2018
ms.keywords: RtlULongToUChar, RtlULongToUChar function [Kernel-Mode Driver Architecture], kernel.rtlulongtouchar, ntintsafe/RtlULongToUChar
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlULongToUChar"
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
- RtlULongToUChar
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongToUChar function


## -description


Converts a value of type <b>ULONG</b> to a value of type <b>UCHAR</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



