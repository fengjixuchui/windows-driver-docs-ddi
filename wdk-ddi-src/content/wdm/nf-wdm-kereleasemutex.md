---
UID: NF:wdm.KeReleaseMutex
title: KeReleaseMutex function (wdm.h)
description: The KeReleaseMutex routine releases a mutex object, and specifies whether the caller is to call one of the KeWaitXxx routines as soon as KeReleaseMutex returns control.
old-location: kernel\kereleasemutex.htm
tech.root: kernel
ms.assetid: d220f913-6111-435d-b617-257edf2a9c68
ms.date: 04/30/2018
ms.keywords: KeReleaseMutex, KeReleaseMutex routine [Kernel-Mode Driver Architecture], k105_4237a9e6-715b-4e40-aab8-9b1458a220ae.xml, kernel.kereleasemutex, wdm/KeReleaseMutex
ms.topic: function
f1_keywords:
 - "wdm/KeReleaseMutex"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeReleaseMutex
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeReleaseMutex function


## -description


The <b>KeReleaseMutex</b> routine releases a mutex object, and specifies whether the caller is to call one of the <b>KeWait<i>Xxx</i></b> routines as soon as <b>KeReleaseMutex</b> returns control. 


## -parameters




### -param Mutex [in, out]

A pointer to an initialized mutex object for which the caller provides the storage.


### -param Wait [in]

Specifies whether the call to <b>KeReleaseMutex</b> is to be immediately followed by a call to one of the <b>KeWait<i>Xxx</i></b> routines. If <b>TRUE</b>, the <b>KeReleaseMutex</b> call must be followed by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>. For more information, see the following Remarks section. 


## -returns



If the return value is zero, the mutex object was released and attained a state of <i>signaled</i>.




## -remarks



For better performance, use fast mutexes or guarded mutexes. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/alternatives-to-mutex-objects">Alternatives to Mutex Objects</a>.

If the mutex object attains a signaled state, an attempt is made to satisfy a wait for the mutex object.

A mutex object can be released only by the thread that currently holds the mutex. If an attempt is made to release a mutex that the thread does not hold or if a mutex was acquired at IRQL = DISPATCH_LEVEL and the thread is not running at DISPATCH_LEVEL (and vice versa), the routine raises a STATUS_ABANDONED or STATUS_MUTEX_NOT_OWNED exception.

When a mutex object attains a signaled state, it is removed from the list of the mutexes that are held by that thread. If this list contains no more entries, the original priority for the thread is restored.

The <b>KeReleaseMutex</b> routine might temporarily raise the IRQL. If the <i>Wait</i> parameter is <b>FALSE</b>, the routine, before it returns, restores the IRQL to the original value that it had at the start of the call.

If <i>Wait</i> = <b>TRUE</b>, the routine returns without lowering the IRQL. In this case, the <b>KeReleaseMutex</b> call must be immediately followed by a <b>KeWait<i>Xxx</i></b> call. By setting <i>Wait</i> = <b>TRUE</b>, the caller can prevent an unnecessary context switch from occurring between the <b>KeReleaseMutex</b> call and the <b>KeWait<i>Xxx</i></b> call. The <b>KeWait<i>Xxx</i></b> routine, before it returns, restores the IRQL to its original value at the start of the <b>KeReleaseMutex</b> call. Although the IRQL disables context switches between the two calls, these calls cannot reliably be used as the start and end of an atomic operation. For example, between these two calls, a thread that is running at the same time on another processor might change the state of the event object or of the target of the wait.

If the caller is executing at IRQL = DISPATCH_LEVEL or in an arbitrary thread context, the <i>Timeout</i> parameter to <b>KeWait<i>Xxx</i></b> must be zero.

If a mutex is acquired recursively, the holding thread must call <b>KeReleaseMutex</b> as many times as it acquired the mutex to set it to the signaled state.

For more information about mutex objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mutex-objects">Mutex Objects</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff545549(v=vs.85)">ExReleaseFastMutex</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff545567(v=vs.85)">ExReleaseFastMutexUnsafe</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializemutex">KeInitializeMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kereadstatemutex">KeReadStateMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
 

 

