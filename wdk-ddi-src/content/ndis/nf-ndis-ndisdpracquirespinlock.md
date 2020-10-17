---
UID: NF:ndis.NdisDprAcquireSpinLock
title: NdisDprAcquireSpinLock macro (ndis.h)
description: The NdisDprAcquireSpinLock function acquires a spin lock so the caller can synchronize access to resources shared among non-ISR driver functions in a multiprocessor-safe way.
old-location: netvista\ndisdpracquirespinlock.htm
tech.root: netvista
ms.assetid: 2e21d2f8-467e-43d3-8261-2373a8b8daa4
ms.date: 05/02/2018
keywords: ["NdisDprAcquireSpinLock macro"]
ms.keywords: NdisDprAcquireSpinLock, NdisDprAcquireSpinLock macro [Network Drivers Starting with Windows Vista], ndis/NdisDprAcquireSpinLock, ndis_spin_lock_ref_c954c605-2544-4911-8ebd-ba0464228437.xml, netvista.ndisdpracquirespinlock
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisDprAcquireSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisDprAcquireSpinLock (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Synch_Function, SpinLock, SpinLockBalanced, SpinLockDpr, SpinLockDprRelease, SpinlockRelease
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisDprAcquireSpinLock
 - ndis/NdisDprAcquireSpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisDprAcquireSpinLock
---

# NdisDprAcquireSpinLock macro


## -description

The 
  <b>NdisDprAcquireSpinLock</b> function acquires a spin lock so the caller can synchronize access to
  resources shared among non-ISR driver functions in a multiprocessor-safe way.

## -parameters

### -param _SpinLock 

[in]
Pointer to an opaque spin lock, already initialized by the caller.

## -remarks

The miniport driver must initialize a variable of type NDIS_SPIN_LOCK with 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> before it calls
    any other 
    <b>Ndis..SpinLock</b> function. The driver must provide resident storage for the spin lock(s) it uses.

<b>NdisDprAcquireSpinLock</b> is an optimized version of 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirespinlock">NdisAcquireSpinLock</a> that a miniport
    driver can call only while running at IRQL = DISPATCH_LEVEL.

After acquiring a spin lock with 
    <b>NdisDprAcquireSpinLock</b>, the caller must release that lock with a call to 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdprreleasespinlock">NdisDprReleaseSpinLock</a>. A miniport
    driver must call 
    <b>NdisDprReleaseSpinLock</b> following each call to 
    <b>NdisDprAcquireSpinLock</b>. Otherwise, a deadlock occurs, hanging the driver.

A spin lock acquired with 
    <b>NdisDprAcquireSpinLock</b> must be released with 
    <b>NdisDprReleaseSpinLock</b>. A spin lock acquired with 
    <b>NdisAcquireSpinLock</b> must be released with 
    <b>NdisReleaseSpinLock</b>.

A driver should never hold a spin lock for an extended period (more than a few instructions). Holding
    a spin lock for longer than 25 microseconds degrades both system and driver performance.

A miniport driver cannot use a spin lock to protect resources that its other functions share with the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> and/or 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_disable_interrupt">
    MiniportDisableInterruptEx</a> functions. Instead, a miniport driver must call 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsynchronizewithinterruptex">
    NdisMSynchronizeWithInterruptEx</a> so that its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_synchronize_interrupt">
    MiniportSynchronizeInterrupt</a> function accesses such shared resources at the same DIRQL at which its    
    <i>MiniportInterrupt</i> and/or 
    <i>MiniportDisableInterruptEx</i> functions do.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization
    and Notification in Network Drivers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_disable_interrupt">MiniportDisableInterruptEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_synchronize_interrupt">
   MiniportSynchronizeInterrupt</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirespinlock">NdisAcquireSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdprreleasespinlock">NdisDprReleaseSpinLock</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsynchronizewithinterruptex">
   NdisMSynchronizeWithInterruptEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a>