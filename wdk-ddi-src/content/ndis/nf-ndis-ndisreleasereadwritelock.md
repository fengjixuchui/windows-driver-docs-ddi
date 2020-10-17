---
UID: NF:ndis.NdisReleaseReadWriteLock
title: NdisReleaseReadWriteLock function (ndis.h)
description: The NdisReleaseReadWriteLock function releases a lock that was acquired in a preceding call to NdisAcquireReadWriteLock.Note  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use NdisReleaseRWLock instead of NdisReleaseReadWriteLock.
old-location: netvista\ndisreleasereadwritelock.htm
tech.root: netvista
ms.assetid: a910ae2d-8a3b-451c-b1f2-a19f7f9f14a2
ms.date: 03/26/2018
keywords: ["NdisReleaseReadWriteLock function"]
ms.keywords: NdisReleaseReadWriteLock, NdisReleaseReadWriteLock function [Network Drivers Starting with Windows Vista], ndis/NdisReleaseReadWriteLock, ndis_read_write_lock_ref_4f0f9891-a4a6-457d-b547-4f5543fbc534.xml, netvista.ndisreleasereadwritelock
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated for NDIS 6.20 and later drivers, which should use NdisReleaseRWLock instead of NdisReleaseReadWriteLock. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReleaseReadWriteLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReleaseReadWriteLock (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Synch_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: Ndis.sys
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
f1_keywords:
 - NdisReleaseReadWriteLock
 - ndis/NdisReleaseReadWriteLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - ndis.sys
api_name:
 - NdisReleaseReadWriteLock
---

# NdisReleaseReadWriteLock function


## -description

The
  <b>NdisReleaseReadWriteLock</b> function releases a lock that was acquired in a preceding call to
  <a href="/previous-versions/ff560696(v=vs.85)">NdisAcquireReadWriteLock</a>.
<div class="alert"><b>Note</b>  The read-write lock interface is deprecated for NDIS 6.20 and later drivers, which should use <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleaserwlock">NdisReleaseRWLock</a> instead of <b>NdisReleaseReadWriteLock</b>.</div><div> </div>

## -parameters

### -param Lock 

[in, out]
A pointer to an <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_rw_lock">NDIS_RW_LOCK</a> variable for the acquired lock to be released.

### -param _Requires_lock_held_

A pointer to an opaque <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_lock_state">LOCK_STATE</a> variable that tracks the state of the lock. This variable exists
     in the interval between the time the caller acquires and releases the lock.

## -remarks

A driver must initialize a lock before calling any other
    Ndis<i>Xxx</i>ReadWriteLock function that is used to acquire or release read or write access to the
    resources that are protected by that lock. The
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializereadwritelock">NdisInitializeReadWriteLock</a> function is used to initialize a lock.

A driver must call the
    <a href="/previous-versions/ff560696(v=vs.85)">NdisAcquireReadWriteLock</a> function
    to acquire a lock before the driver can call
    <b>NdisReleaseReadWriteLock</b>. Each call to
    <b>NdisAcquireReadWriteLock</b> requires a reciprocal call to
    <b>NdisReleaseReadWriteLock</b>.

<b>NdisReleaseReadWriteLock</b> restores the original IRQL that was used by its caller before the call to
    <a href="/previous-versions/ff560696(v=vs.85)">NdisAcquireReadWriteLock</a> was made.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_lock_state">LOCK_STATE</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_rw_lock">NDIS_RW_LOCK</a>



<a href="/previous-versions/ff560696(v=vs.85)">NdisAcquireReadWriteLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializereadwritelock">NdisInitializeReadWriteLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleaserwlock">NdisReleaseRWLock</a>