---
UID: NF:wdm.ExReleaseSpinLockShared
title: ExReleaseSpinLockShared function (wdm.h)
description: The ExReleaseSpinLockShared routine releases ownership of a spin lock that the caller previously acquired for shared access, and restores the IRQL to its original value.
old-location: kernel\exreleasespinlockshared_.htm
tech.root: kernel
ms.assetid: D79FD160-1A03-43F0-B9AB-D74C6176565A
ms.date: 03/28/2018
ms.keywords: ExReleaseSpinLockShared, ExReleaseSpinLockShared routine [Kernel-Mode Driver Architecture], kernel.exreleasespinlockshared_, wdm/ExReleaseSpinLockShared
ms.topic: function
req.header: wdm.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista with SP1.
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
req.irql: DISPATCH_LEVEL (See Remarks.)
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- ExReleaseSpinLockShared
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExReleaseSpinLockShared function


## -description


The <b>ExReleaseSpinLockShared</b> routine releases ownership of a  <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-spin-locks">spin lock</a> that the caller previously acquired for shared access, and restores the IRQL to its original value.


## -parameters




### -param param  [in, out]

A pointer to the spin lock to release. The caller must own this spin lock for shared access.


### -param OldIrql [in]

The interrupt request level (IRQL) to restore. Set this parameter to the KIRQL value that was returned by the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh451053(v=vs.85)">ExAcquireSpinLockShared</a> call that acquired the spin lock.



## -returns



None.




## -remarks



This routine must be called only for a spin lock that is owned by the caller.

On entry to this routine, the caller must be running at IRQL = DISPATCH_LEVEL. Before exiting, <b>ExReleaseSpinLockShared</b> restores the IRQL to the value specified by the <i>OldIrql</i> parameter.

The caller should hold the spin lock only briefly before releasing it. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-spin-locks">Introduction to Spin Locks</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh451053(v=vs.85)">ExAcquireSpinLockShared</a>
 

 

