---
UID: NF:ntintsafe.RtlULongToShort
title: RtlULongToShort function (ntintsafe.h)
description: Converts a value of type ULONG to a value of type SHORT.
old-location: kernel\rtlulongtoshort.htm
tech.root: kernel
ms.assetid: CF44513A-8BFE-453F-A3C1-BF50C86A663E
ms.date: 04/30/2018
ms.keywords: RtlULongToShort, RtlULongToShort function [Kernel-Mode Driver Architecture], kernel.rtlulongtoshort, ntintsafe/RtlULongToShort
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlULongToShort"
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
- RtlULongToShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongToShort function


## -description


Converts a value of type <b>ULONG</b> to a value of type <b>SHORT</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



