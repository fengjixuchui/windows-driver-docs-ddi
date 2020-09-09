---
UID: NF:portcls.IServiceGroup.RequestDelayedService
title: IServiceGroup::RequestDelayedService (portcls.h)
description: The RequestDelayedService method requests service after the specified delay.
old-location: audio\iservicegroup_requestdelayedservice.htm
tech.root: audio
ms.assetid: 045a6c20-2e4e-4669-953d-f8648bf2d718
ms.date: 05/08/2018
keywords: ["IServiceGroup::RequestDelayedService"]
ms.keywords: IServiceGroup interface [Audio Devices],RequestDelayedService method, IServiceGroup.RequestDelayedService, IServiceGroup::RequestDelayedService, RequestDelayedService, RequestDelayedService method [Audio Devices], RequestDelayedService method [Audio Devices],IServiceGroup interface, audio.iservicegroup_requestdelayedservice, audmp-routines_2f9be34c-bff3-46d4-a490-595c8f4311b9.xml, portcls/IServiceGroup::RequestDelayedService
req.header: portcls.h
req.include-header: Portcls.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IServiceGroup::RequestDelayedService
 - portcls/IServiceGroup::RequestDelayedService
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IServiceGroup.RequestDelayedService
---

# IServiceGroup::RequestDelayedService


## -description

The <code>RequestDelayedService</code> method requests service after the specified delay.

## -parameters

### -param ullDelay

#### - ulDelay [in]

Specifies the absolute or relative time at which the timer is to expire. If the value of <i>ulDelay</i> is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units (100-nanosecond intervals). Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.

## -remarks

Before calling <code>RequestDelayedService</code> to request a timer delay, initialize the timer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iservicegroup-supportdelayedservice">IServiceGroup::SupportDelayedService</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iservicegroup-supportdelayedservice">IServiceGroup::SupportDelayedService</a>

