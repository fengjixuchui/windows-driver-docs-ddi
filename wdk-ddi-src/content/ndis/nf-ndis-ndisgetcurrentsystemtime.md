---
UID: NF:ndis.NdisGetCurrentSystemTime
title: NdisGetCurrentSystemTime macro (ndis.h)
description: The NdisGetCurrentSystemTime function returns the current system time, suitable for setting timestamps.
old-location: netvista\ndisgetcurrentsystemtime.htm
tech.root: netvista
ms.assetid: eef32784-ea27-42c0-9a7a-74ce3d76665d
ms.date: 05/02/2018
keywords: ["NdisGetCurrentSystemTime macro"]
ms.keywords: NdisGetCurrentSystemTime, NdisGetCurrentSystemTime macro [Network Drivers Starting with Windows Vista], ndis/NdisGetCurrentSystemTime, ndis_sysinfo_ref_cfd2358c-a52a-43d9-a07b-c64abb3e28b1.xml, netvista.ndisgetcurrentsystemtime
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetCurrentSystemTime (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetCurrentSystemTime (NDIS   5.1)) in Windows XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisGetCurrentSystemTime
 - ndis/NdisGetCurrentSystemTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisGetCurrentSystemTime
---

# NdisGetCurrentSystemTime macro


## -description

The 
  <b>NdisGetCurrentSystemTime</b> function returns the current system time, suitable for setting
  timestamps.

## -parameters

### -param _pSystemTime 

[in]
A pointer to a caller-supplied variable in which this function returns a count of 100-nanosecond
     intervals since January 1, 1601.

## -remarks

An NDIS driver might also call 
    <b>NdisGetCurrentSystemTime</b> if it maintains a count of how many packets it receives within any
    particular interval to tune its performance dynamically. For example, a miniport driver could call 
    <b>NdisGetCurrentSystemTime</b> for each receive interrupt to determine periods of high network traffic,
    when the driver might disable one or more types of interrupts on the NIC and enable a polling 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a> function to process
    receive indications or send requests.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a>