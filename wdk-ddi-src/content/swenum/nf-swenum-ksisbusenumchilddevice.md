---
UID: NF:swenum.KsIsBusEnumChildDevice
title: KsIsBusEnumChildDevice function (swenum.h)
description: The KsIsBusEnumChildDevice function determines if the given device object is a child device of the demand-load bus enumerator object.
old-location: stream\ksisbusenumchilddevice.htm
tech.root: stream
ms.assetid: 7b9aa600-dd47-4ef1-acc8-02fb1b4f51ce
ms.date: 04/23/2018
keywords: ["KsIsBusEnumChildDevice function"]
ms.keywords: KsIsBusEnumChildDevice, KsIsBusEnumChildDevice function [Streaming Media Devices], ksfunc_5718ba1d-d377-40f8-8972-7005f4064e7c.xml, stream.ksisbusenumchilddevice, swenum/KsIsBusEnumChildDevice
f1_keywords:
 - "swenum/KsIsBusEnumChildDevice"
 - "KsIsBusEnumChildDevice"
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsIsBusEnumChildDevice
targetos: Windows
req.typenames: 
---

# KsIsBusEnumChildDevice function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsIsBusEnumChildDevice</b> function determines if the given device object is a child device of the demand-load bus enumerator object. 


## -parameters




### -param DeviceObject [in]

Pointer to a device object.


### -param ChildDevice [out]

Pointer to a BOOLEAN to receive the result. <b>KsIsBusEnumChildDevice</b> sets this to <b>TRUE</b> if the given device object is a child device of the demand-load bus enumerator object, or <b>FALSE</b> otherwise.


## -returns



Returns STATUS_SUCCESS if the given device object's device extension is valid; otherwise, it returns an error code.



