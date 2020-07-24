---
UID: NF:ntintsafe.RtlUShortToShort
title: RtlUShortToShort function (ntintsafe.h)
description: Converts a value of type USHORT to a value of type SHORT.
old-location: kernel\rtlushorttoshort.htm
tech.root: kernel
ms.assetid: 055B5605-2EBB-4B09-9C21-A8288D0DB3CD
ms.date: 04/30/2018
keywords: ["RtlUShortToShort function"]
ms.keywords: RtlUShortToShort, RtlUShortToShort function [Kernel-Mode Driver Architecture], kernel.rtlushorttoshort, ntintsafe/RtlUShortToShort
f1_keywords:
 - "ntintsafe/RtlUShortToShort"
 - "RtlUShortToShort"
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
- RtlUShortToShort
targetos: Windows
req.typenames: 
---

# RtlUShortToShort function


## -description


Converts a value of type <b>USHORT</b> to a value of type <b>SHORT</b>.


## -parameters




### -param usOperand [in]

The value to be converted.


### -param psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.



