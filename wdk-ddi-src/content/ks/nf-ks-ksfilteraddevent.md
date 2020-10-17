---
UID: NF:ks.KsFilterAddEvent
title: KsFilterAddEvent function (ks.h)
description: The KsFilterAddEvent function adds an event to Filter's event list.
old-location: stream\ksfilteraddevent.htm
tech.root: stream
ms.assetid: e93491c1-bd6d-4d89-b55f-10439b0f5eec
ms.date: 04/23/2018
keywords: ["KsFilterAddEvent function"]
ms.keywords: KsFilterAddEvent, KsFilterAddEvent function [Streaming Media Devices], avfunc_a00691e6-cae6-40ae-9776-1b6d09e01d73.xml, ks/KsFilterAddEvent, stream.ksfilteraddevent
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
 - KsFilterAddEvent
 - ks/KsFilterAddEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsFilterAddEvent
---

# KsFilterAddEvent function


## -description

The<b> KsFilterAddEvent</b> function adds an event to <i>Filter</i>'s event list.

## -parameters

### -param Filter 

[in]
<i>A pointer</i> to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure representing the filter to which to add a specified event.

### -param EventEntry 

[in]
<i>A pointer</i> to an <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a> structure describing the event to add to <i>Filter</i>.

## -remarks

This function is an inline function call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksaddevent">KsAddEvent</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksaddevent">KsAddEvent</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgenerateevents">KsGenerateEvents</a>