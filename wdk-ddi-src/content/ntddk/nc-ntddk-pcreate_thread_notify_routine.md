---
UID: NC:ntddk.PCREATE_THREAD_NOTIFY_ROUTINE
title: PCREATE_THREAD_NOTIFY_ROUTINE (ntddk.h)
description: A callback routine implemented by a driver to notify the caller when a thread is created or deleted.
old-location: kernel\pcreate_thread_notify_routine.htm
tech.root: kernel
ms.assetid: AAA62659-D12C-4EEC-8D74-6138B34128CE
ms.date: 04/30/2018
ms.keywords: PCREATE_THREAD_NOTIFY_ROUTINE, PCREATE_THREAD_NOTIFY_ROUTINE callback, SetCreateThreadNotifyRoutine, SetCreateThreadNotifyRoutine callback function [Kernel-Mode Driver Architecture], kernel.pcreate_thread_notify_routine, ntddk/SetCreateThreadNotifyRoutine
ms.topic: callback
f1_keywords:
 - "ntddk/SetCreateThreadNotifyRoutine"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ntddk.h
api_name:
- SetCreateThreadNotifyRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCREATE_THREAD_NOTIFY_ROUTINE callback function


## -description


A callback routine implemented by a driver to notify the caller when a thread is created or deleted.
<div class="alert"><b>Warning</b>  The actions that  you can perform in this routine are restricted for safe calls. See <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/windows-kernel-mode-process-and-thread-manager#best">Best Practices</a>. </div><div> </div>

## -parameters




### -param ProcessId [in]

The process ID of the process.


### -param ThreadId [in]

The thread ID of the thread.


### -param Create [in]

Indicates whether the thread was created (<b>TRUE</b>) or deleted (<b>FALSE</b>).


## -remarks



Highest-level drivers can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutineex">PsSetCreateThreadNotifyRoutineEx</a> to register their thread-creation notify routine.

The driver's thread-notify routine runs at IRQL = PASSIVE_LEVEL or APC_LEVEL. When a thread is created, the thread-notify routine runs in the context of the thread that created the new thread. When a thread is deleted, the thread-notify routine runs in the context of this thread when the thread exits. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutineex">PsSetCreateThreadNotifyRoutineEx</a>
 

 

