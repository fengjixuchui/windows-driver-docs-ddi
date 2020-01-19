---
UID: NF:ntifs.KeInsertQueue
title: KeInsertQueue function (ntifs.h)
description: The KeInsertQueue routine inserts an entry at the tail of the given queue if it cannot immediately use the entry to satisfy a thread wait.
old-location: ifsk\keinsertqueue.htm
tech.root: ifsk
ms.assetid: 0aee6102-e9e3-41dc-a222-36bebb3d4294
ms.date: 04/16/2018
ms.keywords: KeInsertQueue, KeInsertQueue routine [Installable File System Drivers], ifsk.keinsertqueue, keref_0e1ad47f-c38b-40e8-8629-8d970d5e1a72.xml, ntifs/KeInsertQueue
ms.topic: function
f1_keywords:
 - "ntifs/KeInsertQueue"
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeInsertQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeInsertQueue function


## -description


The <b>KeInsertQueue</b> routine inserts an entry at the tail of the given queue if it cannot immediately use the entry to satisfy a thread wait. 


## -parameters




### -param Queue [in, out]

Pointer to an initialized queue object for which the caller provides resident storage in nonpaged pool. 


### -param Entry [in, out]

Pointer to an entry to be queued. This pointer must be a resident system-space address. 


## -returns



<b>KeInsertQueue</b> returns the previous signal state of the given <i>Queue</i>. If it was set to zero (that is, not signaled) before <b>KeInsertQueue</b> was called, <b>KeInsertQueue</b> returns zero, meaning that no entries were queued. If it was nonzero (signaled), <b>KeInsertQueue</b> returns the number of entries that were queued before <b>KeInsertQueue</b> was called. 




## -remarks



Entries to be queued by <b>KeInsertQueue</b> must be allocated from nonpaged pool. For example, memory for caller-defined entries can be allocated with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>. If the caller allocates entries of a fixed size, creating a lookaside list with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializenpagedlookasidelist">ExInitializeNPagedLookasideList</a> and allocating from it with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a> is more efficient than making frequent calls to <b>ExAllocatePoolWithTag</b>, particularly for entries whose size is not a multiple of PAGE_SIZE. 

If any threads are waiting on the queue object when <b>KeInsertQueue</b> is called, a single thread's wait is satisfied by this call. The thread is dispatched for execution with the given <i>Entry</i> pointer. 

If no threads are currently waiting on the queue object when <b>KeInsertQueue</b> is called, the given entry is inserted in the queue, and the queue object's signal state is incremented. 

For more information about using driver-managed internal queues, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Driver-Managed Queues</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializenpagedlookasidelist">ExInitializeNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-keinitializequeue">KeInitializeQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-keinsertheadqueue">KeInsertHeadQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-keremovequeue">KeRemoveQueue</a>
 

 

