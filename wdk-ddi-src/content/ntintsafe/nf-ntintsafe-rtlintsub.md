---
UID: NF:ntintsafe.RtlIntSub
title: RtlIntSub function (ntintsafe.h)
description: Subtracts one value of type INT from another.
old-location: kernel\rtlintsub.htm
tech.root: kernel
ms.assetid: 68BBD6B8-5C7C-4FE5-97F7-473A9510400F
ms.date: 04/30/2018
ms.keywords: RtlIntSub, RtlIntSub function [Kernel-Mode Driver Architecture], kernel.rtlintsub, ntintsafe/RtlIntSub
ms.topic: function
f1_keywords:
 - "ntintsafe/RtlIntSub"
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
- RtlIntSub
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIntSub function


## -description


Subtracts one value of type <b>INT</b> from another.


## -parameters




### -param iMinuend [in]

The value from which <i>iSubtrahend</i> is subtracted.


### -param iSubtrahend [in]

The value to subtract from <i>iMinuend</i>.


### -param piResult

<p>A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>




## -remarks



This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt32Sub
</li>
<li>RtlLong32Sub
</li>
</ul>


