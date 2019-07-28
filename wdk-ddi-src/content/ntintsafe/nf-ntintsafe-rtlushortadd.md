---
UID: NF:ntintsafe.RtlUShortAdd
title: RtlUShortAdd function (ntintsafe.h)
description: Adds two values of type USHORT.
old-location: kernel\rtlushortadd.htm
tech.root: kernel
ms.assetid: 07167C7E-E8EB-41E3-B2E3-7B9E9CCC5465
ms.date: 04/30/2018
ms.keywords: RtlUShortAdd, RtlUShortAdd function [Kernel-Mode Driver Architecture], kernel.rtlushortadd, ntintsafe/RtlUShortAdd
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlUShortAdd"
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
- RtlUShortAdd
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUShortAdd function


## -description


Adds two values of type <b>USHORT</b>.


## -parameters




### -param usAugend [in]

The first value in the equation.


### -param usAddend [in]

The value to add to <i>usAugend</i>.


### -param pusResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



