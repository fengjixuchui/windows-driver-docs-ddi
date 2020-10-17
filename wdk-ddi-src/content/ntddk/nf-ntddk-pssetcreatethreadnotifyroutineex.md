---
UID: NF:ntddk.PsSetCreateThreadNotifyRoutineEx
title: PsSetCreateThreadNotifyRoutineEx function (ntddk.h)
description: The PsSetCreateThreadNotifyRoutineEx routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted.
old-location: kernel\pssetcreatethreadnotifyroutineex.htm
tech.root: kernel
ms.assetid: 586688EC-51B1-488E-BFC6-7796C37593BF
ms.date: 04/30/2018
keywords: ["PsSetCreateThreadNotifyRoutineEx function"]
ms.keywords: PsSetCreateThreadNotifyRoutineEx, PsSetCreateThreadNotifyRoutineEx routine [Kernel-Mode Driver Architecture], kernel.pssetcreatethreadnotifyroutineex, ntddk/PsSetCreateThreadNotifyRoutineEx
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PsSetCreateThreadNotifyRoutineEx
 - ntddk/PsSetCreateThreadNotifyRoutineEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsSetCreateThreadNotifyRoutineEx
---

# PsSetCreateThreadNotifyRoutineEx function


## -description

The <b>PsSetCreateThreadNotifyRoutineEx</b> routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted.

## -parameters

### -param NotifyType 

[in]
A <a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_pscreatethreadnotifytype">PSCREATETHREADNOTIFYTYPE</a> value that   indicates the type of thread notification.

### -param NotifyInformation 

[in]
Provides the address of the notification information
        for the specified type of thread notification.

## -returns

<b>PsSetCreateThreadNotifyRoutineEx</b> either returns STATUS_SUCCESS or it returns STATUS_INSUFFICIENT_RESOURCES if it failed the callback registration.

## -remarks

Highest-level drivers can call <b>PsSetCreateThreadNotifyRoutineEx</b> to set up their thread-creation notify routines.

For example, an IFS or highest-level system-profiling driver might register such a thread-creation callback to track the system-wide creation and deletion of threads against the driver's internal state.

If <i>NotifyType</i> is <b>PsCreateThreadNotifyNonSystem</b>, the  <b>PsSetCreateThreadNotifyRoutineEx</b> routine differs from <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a> in the context in which the callback is executed. With <b>PsSetCreateThreadNotifyRoutine</b>, the callback is executed on the creator thread. With <b>PsSetCreateThreadNotifyRoutineEx</b>, the callback is executed on the newly created thread.

A driver must remove any callback function it registers before it unloads. You can remove the callback by calling the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremovecreatethreadnotifyroutine">PsRemoveCreateThreadNotifyRoutine</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentprocessid">PsGetCurrentProcessId</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthreadid">PsGetCurrentThreadId</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psissystemthread">PsIsSystemThread</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremovecreatethreadnotifyroutine">PsRemoveCreateThreadNotifyRoutine</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">PsSetCreateProcessNotifyRoutine</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetloadimagenotifyroutine">PsSetLoadImageNotifyRoutine</a>