---
UID: NF:ks.KsDisableEvent
title: KsDisableEvent function (ks.h)
description: The KsDisableEvent function disables events requested through IOCTL_KS_DISABLE_EVENT.
old-location: stream\ksdisableevent.htm
tech.root: stream
ms.assetid: 4af94bc4-9df3-4b37-a810-303748cc4b75
ms.date: 04/23/2018
keywords: ["KsDisableEvent function"]
ms.keywords: KsDisableEvent, KsDisableEvent function [Streaming Media Devices], ks/KsDisableEvent, ksfunc_e430d502-c847-43ee-bdea-d53200f45e53.xml, stream.ksdisableevent
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsDisableEvent
 - ks/KsDisableEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsDisableEvent
---

# KsDisableEvent function


## -description

The <b>KsDisableEvent </b>function disables events requested through IOCTL_KS_DISABLE_EVENT. It responds to all events previously enabled through <b>KsEnableEvent</b>. If the input buffer length is zero, it is assumed that all events on the list are to be disabled. This function can only be called at PASSIVE_LEVEL.

## -parameters

### -param Irp 

[in]
Specifies the IRP passed to the removal function, which uses the IRP to obtain context information. The file object associated with the IRP is used to compare against the file object originally specified when enabling the event. This allows a single event list to be used for multiple clients differentiated by file objects.

### -param EventsList 

[in, out]
Points to the head of the list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a> items on which the event may be found. If a client uses multiple event lists and does not know what list this event is on, the client can call this function multiple times. An event not found will return STATUS_UNSUCCESSFUL.

### -param EventsFlags 

[in]
Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksevents_locktype">KSEVENTS_LOCKTYPE</a> flag specifying the type of exclusion lock to be used in accessing the event list. If no flag is set, then no lock is taken.

### -param EventsLock 

[in]
Used to synchronize access to an element on the list. After the element has been accessed, it is marked as being deleted so that subsequent removal requests fail. The lock is then released after calling the removal function, if any. The removal function must synchronize with event generation before actually removing the element from the list.

## -returns

The <b>KsDisableEvent </b>function returns STATUS_SUCCESS if successful, or an error specific to the event being enabled. The function always sets the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP to zero. It does not set the IO_STATUS_BLOCK.Status field, nor does it complete the IRP.

## -remarks

It is important that the remove handler synchronize with event generation to ensure that when the event is removed from the list, it is not currently being serviced. Access to this list is assumed to be controlled with the lock passed.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksenableevent">KsEnableEvent</a>

