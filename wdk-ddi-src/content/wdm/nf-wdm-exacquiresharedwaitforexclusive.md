---
UID: NF:wdm.ExAcquireSharedWaitForExclusive
title: ExAcquireSharedWaitForExclusive function (wdm.h)
description: The ExAcquireSharedWaitForExclusive routine acquires the given resource for shared access if shared access can be granted and there are no exclusive waiters.
old-location: kernel\exacquiresharedwaitforexclusive.htm
tech.root: kernel
ms.assetid: 745b014d-7ab4-4e07-a24c-7a74949a9d7b
ms.date: 04/30/2018
keywords: ["ExAcquireSharedWaitForExclusive function"]
ms.keywords: ExAcquireSharedWaitForExclusive, ExAcquireSharedWaitForExclusive routine [Kernel-Mode Driver Architecture], k102_505fe2a0-5751-4481-a545-2091828463ce.xml, kernel.exacquiresharedwaitforexclusive, wdm/ExAcquireSharedWaitForExclusive
f1_keywords:
 - "wdm/ExAcquireSharedWaitForExclusive"
 - "ExAcquireSharedWaitForExclusive"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte3, WithinCriticalRegion, HwStorPortProhibitedDDIs, SpNoWait, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExAcquireSharedWaitForExclusive
targetos: Windows
req.typenames: 
---

# ExAcquireSharedWaitForExclusive function


## -description


The <b>ExAcquireSharedWaitForExclusive</b> routine acquires the given resource for shared access if shared access can be granted and there are no exclusive waiters. 


## -parameters




### -param Resource [in, out]

A pointer to the resource to be acquired for shared access.


### -param Wait [in]

Specifies the routine's behavior whenever the resource cannot be acquired immediately. If <b>TRUE</b>, the caller is put into a wait state until the resource can be acquired. If <b>FALSE</b>, the routine immediately returns, regardless of whether the resource can be acquired. 


## -returns



<b>ExAcquireSharedWaitForExclusive</b> returns <b>TRUE</b> if the requested access is granted or an exclusive owner releases the resource. This routine returns <b>FALSE</b> if the input <i>Wait</i> is <b>FALSE</b> and shared access cannot be granted immediately. 




## -remarks



Most drivers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a> instead of <b>ExAcquireSharedWaitForExclusive</b>.

The caller can release the resource by calling either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaseresourcelite">ExReleaseResourceLite</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545585">ExReleaseResourceForThreadLite</a>.

If shared access cannot be granted immediately, the caller can wait for other threads to acquire and release exclusive ownership of the resource.

Whether or when the caller is given shared access to the given resource depends on the following:

<ul>
<li>
If the resource is currently unowned, shared access is granted immediately to the current thread.

</li>
<li>
If the caller already has exclusive access to the resource, the current thread is granted the same type of access recursively. 

</li>
<li>
If the resource is currently owned as shared and there are no pending attempts to acquire exclusive access, shared access is granted to the caller immediately. 

</li>
<li>
If the resource is currently owned as shared but there is a pending attempt to acquire exclusive access, the caller either is put into a wait state (<i>Wait</i> set to <b>TRUE</b>) or <b>ExAcquireSharedWaitForExclusive</b> returns <b>FALSE</b>.

When the current thread waits to acquire the resource until after a pending exclusive ownership has been released, <b>ExAcquireSharedWaitForExclusive</b> returns <b>TRUE</b> when the current thread is granted shared access to the resource and resumes execution. 

</li>
</ul>
The behavior of <b>ExAcquireSharedWaitForExclusive</b> is identical to that of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a> unless the calling thread already owns the resource as shared and there are exclusive waiters. In that case, <b>ExAcquireSharedWaitForExclusive</b> allows the exclusive waiters to acquire exclusive ownership of the resource.

If the caller specifies <b>TRUE</b> for the <i>Wait</i> parameter, the caller blocks until another thread frees the resource on behalf of the caller, using <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mmcreatemdl">ExReleaseResourceForThread</a>. Driver writers must be careful to ensure that another thread actually releases the resource; otherwise the caller is deadlocked. <b>ExAcquireResourceSharedLite</b> does not have this property, so drivers should use that routine unless they require the particular behavior of <b>ExAcquireSharedWaitForExclusive</b>.

Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a>. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keleavecriticalregion">KeLeaveCriticalRegion</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs">Disabling APCs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544367">ExAcquireSharedStarveExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544558">ExConvertExclusiveToSharedLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exgetexclusivewaitercount">ExGetExclusiveWaiterCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredexclusivelite">ExIsResourceAcquiredExclusiveLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredsharedlite">ExIsResourceAcquiredSharedLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mmcreatemdl">ExReleaseResourceForThread</a>
 

 

