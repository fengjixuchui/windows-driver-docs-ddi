---
UID: NF:ntintsafe.RtlIntPtrAdd
title: RtlIntPtrAdd function (ntintsafe.h)
description: Adds two values of type INT_PTR.
old-location: kernel\rtlintptradd.htm
tech.root: kernel
ms.assetid: 97873113-7B0B-4121-B074-5B73D59489F4
ms.date: 04/30/2018
keywords: ["RtlIntPtrAdd function"]
ms.keywords: RtlIntPtrAdd, RtlIntPtrAdd function [Kernel-Mode Driver Architecture], kernel.rtlintptradd, ntintsafe/RtlIntPtrAdd
f1_keywords:
 - "ntintsafe/RtlIntPtrAdd"
 - "RtlIntPtrAdd"
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
- RtlIntPtrAdd
targetos: Windows
req.typenames: 
---

# RtlIntPtrAdd function


## -description


Adds two values of type <b>INT_PTR</b>.


## -parameters




### -param iAugend [in]

The first value in the equation.


### -param iAddend [in]

The value to add to <i>iAugend</i>.


### -param piResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



