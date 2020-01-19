---
UID: NF:ks.KsSetDefaultClockState
title: KsSetDefaultClockState function (ks.h)
description: The KsSetDefaultClockState function sets the current state of the clock that is used to reflect the current state of the underlying filter pin.
old-location: stream\kssetdefaultclockstate.htm
tech.root: stream
ms.assetid: 5893f4ff-0eb5-4cdc-8f58-f7654c1ce9fc
ms.date: 04/23/2018
ms.keywords: KsSetDefaultClockState, KsSetDefaultClockState function [Streaming Media Devices], ks/KsSetDefaultClockState, ksfunc_a57f26f0-cd4a-4d80-a090-788aef1ccf4b.xml, stream.kssetdefaultclockstate
ms.topic: function
f1_keywords:
 - "ks/KsSetDefaultClockState"
req.header: ks.h
req.include-header: Ks.h
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
- KsSetDefaultClockState
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsSetDefaultClockState function


## -description


The <b>KsSetDefaultClockState</b> function sets the current state of the clock that is used to reflect the current state of the underlying filter pin. The owner of the default clock is expected to serialize access to this function and to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kssetdefaultclocktime">KsSetDefaultClockTime</a>.

The function can be called at DISPATCH_LEVEL.


## -parameters




### -param DefaultClock [in]

Specifies an initialize default clock structure that is shared among any instance of the default clock for the parent.


### -param State [in]

Specifies the new state to set the clock.


## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetdefaultclockstate">KsGetDefaultClockState</a>
 

 

