---
UID: NF:ntintsafe.RtlUShortSub
title: RtlUShortSub function (ntintsafe.h)
description: Subtracts one value of type USHORT from another.
old-location: kernel\rtlushortsub.htm
tech.root: kernel
ms.assetid: 1C0392AE-F3BD-4F42-9094-87228B7C3E10
ms.date: 04/30/2018
ms.keywords: RtlUShortSub, RtlUShortSub function [Kernel-Mode Driver Architecture], kernel.rtlushortsub, ntintsafe/RtlUShortSub
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlUShortSub"
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
- RtlUShortSub
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUShortSub function


## -description


Subtracts one value of type <b>USHORT</b> from another.


## -parameters




### -param usMinuend [in]

The value from which <i>usSubtrahend</i> is subtracted.


### -param usSubtrahend [in]

The value to subtract from <i>usMinuend</i>.


### -param pusResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.



