---
UID: NF:ks.KsCreateDefaultClock
title: KsCreateDefaultClock function (ks.h)
description: Given an IRP_MJ_CREATE request, the KsCreateDefaultClock function creates a default clock that uses the system clock as a time base and associates the IoGetCurrentIrpStackLocation(Irp)-&gt;FileObject with the clock using an internal dispatch table (KSDISPATCH_TABLE). Does not complete the IRP or set the status in the IRP.The KsCreateDefaultClock function can only be called at PASSIVE_LEVEL.
old-location: stream\kscreatedefaultclock.htm
tech.root: stream
ms.assetid: 38ac85bc-9ace-4e70-a886-92e18afb32db
ms.date: 06/25/2020
keywords: ["KsCreateDefaultClock function"]
ms.keywords: KsCreateDefaultClock, KsCreateDefaultClock function [Streaming Media Devices], ks/KsCreateDefaultClock, ksfunc_eb8617e1-d6e0-434d-bace-cec6b2b1cce1.xml, stream.kscreatedefaultclock
f1_keywords:
 - "ks/KsCreateDefaultClock"
 - "KsCreateDefaultClock"
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
- KsCreateDefaultClock
targetos: Windows
req.typenames: 
---

# KsCreateDefaultClock function

## -description

Given an IRP_MJ_CREATE request, the **KsCreateDefaultClock** function creates a default clock that uses the system clock as a time base and associates the IoGetCurrentIrpStackLocation(Irp)->FileObject with the clock using an internal dispatch table (KSDISPATCH_TABLE).  Does not complete the IRP or set the status in the IRP.

The **KsCreateDefaultClock** function can only be called at PASSIVE_LEVEL.

## -parameters

### -param Irp [in]

Specifies the IRP with the clock-create request being handled.

### -param DefaultClock [in]

Specifies an initialize default clock structure that is shared among any instance of the default clock for the parent.

## -returns

The **KsCreateDefaultClock** function returns STATUS_SUCCESS if successful, or an error if unsuccessful.

## -remarks

The clock can be created after using **KsAllocateDefaultClock** to create and initialize the internal structures for a default clock instance. After initialization, many file objects can be created against the same underlying default clock instance.

## -see-also

[KsAllocateDefaultClock](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedefaultclock)
