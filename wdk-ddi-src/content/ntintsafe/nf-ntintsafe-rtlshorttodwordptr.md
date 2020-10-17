---
UID: NF:ntintsafe.RtlShortToDWordPtr
title: RtlShortToDWordPtr function (ntintsafe.h)
description: Converts a value of type SHORT to a value of type DWORD_PTR.
old-location: kernel\rtlshorttodwordptr.htm
tech.root: kernel
ms.assetid: 0ABB3DBF-117D-491D-85A3-68E9280CFC6C
ms.date: 04/30/2018
keywords: ["RtlShortToDWordPtr function"]
ms.keywords: RtlShortToDWordPtr, RtlShortToDWordPtr function [Kernel-Mode Driver Architecture], kernel.rtlshorttodwordptr, ntintsafe/RtlShortToDWordPtr
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlShortToDWordPtr
 - ntintsafe/RtlShortToDWordPtr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntintsafe.h
api_name:
 - RtlShortToDWordPtr
---

# RtlShortToDWordPtr function


## -description

Converts a value of type <b>SHORT</b> to a value of type <b>DWORD_PTR</b>.

## -parameters

### -param sOperand 

[in]
The value to be converted.

### -param pdwResult 

[out]
A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -returns

Returns STATUS_SUCCESS if the operation is successful. 

See the implementation of this helper function in `ntintsafe.h` in the WDK for possible error return values. 

## -remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li></li>
</ul>

