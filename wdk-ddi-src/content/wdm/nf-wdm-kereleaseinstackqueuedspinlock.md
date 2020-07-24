---
UID: NF:wdm.KeReleaseInStackQueuedSpinLock
title: KeReleaseInStackQueuedSpinLock function (wdm.h)
description: The KeReleaseInStackQueuedSpinLock routine releases a queued spin lock acquired by KeAcquireInStackQueuedSpinLock.
old-location: kernel\kereleaseinstackqueuedspinlock.htm
tech.root: kernel
ms.assetid: 5c36df75-6a95-47bb-99d8-14d87c102be4
ms.date: 04/30/2018
keywords: ["KeReleaseInStackQueuedSpinLock function"]
ms.keywords: KeReleaseInStackQueuedSpinLock, KeReleaseInStackQueuedSpinLock routine [Kernel-Mode Driver Architecture], k105_1904b4b2-4f31-4061-895f-8564a1de04f6.xml, kernel.kereleaseinstackqueuedspinlock, wdm/KeReleaseInStackQueuedSpinLock
f1_keywords:
 - "wdm/KeReleaseInStackQueuedSpinLock"
 - "KeReleaseInStackQueuedSpinLock"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: MarkingQueuedIrps, QueuedSpinLock, QueuedSpinLockRelease, HwStorPortProhibitedDDIs, QueuedSpinLock(storport), QueuedSpinLockRelease(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib; Ntoskrnl.lib
req.dll: Hal.dll; Ntoskrnl.exe
req.irql: DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Hal.dll
- Ntoskrnl.exe
api_name:
- KeReleaseInStackQueuedSpinLock
targetos: Windows
req.typenames: 
---

# KeReleaseInStackQueuedSpinLock function


## -description


The <b>KeReleaseInStackQueuedSpinLock</b> routine releases a queued spin lock acquired by <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551899(v=vs.85)">KeAcquireInStackQueuedSpinLock</a>.


## -parameters




### -param LockHandle [in]

Specifies the queued spin lock handle initialized by the call to <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551899(v=vs.85)">KeAcquireInStackQueuedSpinLock</a> that acquired the lock.


## -remarks



This routine restores the original IRQL that the operating system saved at the beginning of the <b>KeAcquireInStackQueuedSpinLock</b> call.

For more information about queued spin locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/queued-spin-locks">Queued Spin Locks</a>.

Use Hal.lib on 32-bit versions of Windows and Ntoskrnl.lib on 64-bit versions of Windows.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KLOCK_QUEUE_HANDLE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551899(v=vs.85)">KeAcquireInStackQueuedSpinLock</a>
 

 

