---
UID: NF:ndis.NdisCancelTimerObject
title: NdisCancelTimerObject function (ndis.h)
description: The NdisCancelTimerObject function cancels a timer object that is associated with a previous call to the NdisSetTimerObject function.
old-location: netvista\ndiscanceltimerobject.htm
tech.root: netvista
ms.assetid: b66652b7-2e02-49f5-a7e3-60ff35363a19
ms.date: 05/02/2018
keywords: ["NdisCancelTimerObject function"]
ms.keywords: NdisCancelTimerObject, NdisCancelTimerObject function [Network Drivers Starting with Windows Vista], ndis/NdisCancelTimerObject, ndis_timer_ref_39b68ae4-4fd7-4609-aebc-e2be21bead04.xml, netvista.ndiscanceltimerobject
f1_keywords:
 - "ndis/NdisCancelTimerObject"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Timer_Function, PeriodicTimer
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: See Remarks section
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisCancelTimerObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCancelTimerObject function


## -description


The 
  <b>NdisCancelTimerObject</b> function cancels a timer object that is associated with a previous call to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a> function.


## -parameters




### -param TimerObject [in]

A handle to a timer object that NDIS provides when a driver calls the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">
     NdisAllocateTimerObject</a> function.


## -returns



<b>NdisCancelTimerObject</b> returns <b>TRUE</b> if the specified timer object is in the system timer queue;
     otherwise, it returns <b>FALSE</b>.




## -remarks



A call to 
    <b>NdisCancelTimerObject</b> cancels execution of a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a> function, provided
    that the last specified timeout interval has not yet expired.

NDIS drivers should call 
    <b>NdisCancelTimerObject</b> first when they are halting or unloading to ensure that a 
    <i>NetTimerCallback</i> function does not attempt to access resources that the driver has already
    released.

If a nonzero value was specified in the 
    <i>MillisecondsPeriod</i> parameter of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a> function, the timer is known as a <i>periodic timer</i>. If a zero value was specified in the <i>MillisecondsPeriod</i> parameter, the timer is known as a <i>one-shot timer</i>. The following points apply to canceling both types of timers:

<ul>
<li>
If  the caller of
    <b>NdisCancelTimerObject</b> is canceling a periodic timer, it must be running at IRQL = PASSIVE_LEVEL. Otherwise, the caller of 
    <b>NdisCancelTimerObject</b> should be running at IRQL <= DISPATCH_LEVEL.

</li>
<li>
If  the caller of
    <b>NdisCancelTimerObject</b> is canceling a periodic timer, <b>NdisCancelTimerObject</b> calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keflushqueueddpcs">KeFlushQueuedDpcs</a> to ensure that the timer is not currently running. Therefore, the caller is not required to have a separate synchronization mechanism to ensure that the timer is not currently being executed on another processor.

If  the caller of
    <b>NdisCancelTimerObject</b> is canceling a one-shot timer, the caller is required to have a separate synchronization mechanism to ensure the timer is not currently running on another processor. For example, the caller could call <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-wait-for-mutex">NDIS_WAIT_FOR_MUTEX</a> in order to wait for the timer thread to signal a mutex object when the thread is about to complete.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronization-and-notification-in-network-drivers">Synchronization and Notification in Network Drivers</a>.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a>
 

 

