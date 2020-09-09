---
UID: NF:wdm.KeWaitForSingleObject
title: KeWaitForSingleObject function (wdm.h)
description: The KeWaitForSingleObject routine puts the current thread into a wait state until the given dispatcher object is set to a signaled state or (optionally) until the wait times out.
old-location: kernel\kewaitforsingleobject.htm
tech.root: kernel
ms.assetid: 65a1aa46-571b-46f7-b60e-ef8c6dc14d39
ms.date: 04/30/2018
keywords: ["KeWaitForSingleObject function"]
ms.keywords: KeWaitForMutexObject, KeWaitForSingleObject, KeWaitForSingleObject routine [Kernel-Mode Driver Architecture], k105_de338bec-f7ef-4780-85e6-592a24314145.xml, kernel.kewaitforsingleobject, wdm/KeWaitForSingleObject
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequestStatusCheck, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildDeviceControlWait, IoBuildDeviceControlWaitTimeout, IoBuildFsdIrpSignalEventInCompletionTimeout, IoBuildSynchronousFsdRequestWait, IoBuildSynchronousFsdRequestWaitTimeout, IrpProcessingComplete, IrqlKeWaitForMutexObject, LowerDriverReturn, MarkIrpPending2, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControlInternal, RemoveLockForwardRead, RemoveLockForwardWrite, StartDeviceWait, StartDeviceWait2, StartDeviceWait3, StartDeviceWait4, HwStorPortProhibitedDDIs, SpNoWait
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - KeWaitForSingleObject
 - wdm/KeWaitForSingleObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeWaitForSingleObject
---

# KeWaitForSingleObject function


## -description

The **KeWaitForSingleObject** routine puts the current thread into a wait state until the given dispatcher object is set to a signaled state or (optionally) until the wait times out.

## -parameters

### -param Object 

[in]
Pointer to an initialized dispatcher object (event, mutex, semaphore, thread, or timer) for which the caller supplies the storage.

### -param WaitReason 

[in]
Specifies the reason for the wait. A driver should set this value to **Executive**, unless it is doing work on behalf of a user and is running in the context of a user thread, in which case it should set this value to **UserRequest**.

### -param WaitMode 

[in]
Specifies whether the caller waits in **KernelMode** or **UserMode**. Lowest-level and intermediate drivers should specify **KernelMode**. If the given *Object* is a mutex, the caller must specify **KernelMode**.

### -param Alertable 

[in]
Specifies a Boolean value that is **TRUE** if the wait is alertable and **FALSE** otherwise.

### -param Timeout 

[in, optional]
Pointer to a time-out value that specifies the absolute or relative time, in 100-nanosecond units, at which the wait is to be completed.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes. 

If **Timeout* = 0, the routine returns without waiting. If the caller supplies a **NULL** pointer, the routine waits indefinitely until the dispatcher object is set to the signaled state. For more information, see the following Remarks section.

## -returns

**KeWaitForSingleObject** can return one of the following.

> [!NOTE]
> The NT_SUCCESS macro recognizes all of these status values as "success" values.

|Return code|Description|
|--- |--- |
|**STATUS_SUCCESS**|The dispatcher object specified by the _Object_ parameter satisfied the wait.|
|**STATUS_ALERTED**|The wait was interrupted to deliver an alert to the calling thread.|
|**STATUS_USER_APC**|The wait was interrupted to deliver a user asynchronous procedure call (APC) to the calling thread.|
|**STATUS_TIMEOUT**|A time-out occurred before the object was set to a signaled state. This value can be returned when the specified set of wait conditions cannot be immediately met and _Timeout_ is set to zero.|

## -syntax

```cpp
NTSTATUS
KeWaitForSingleObject (
    PVOID Object,
    KWAIT_REASON WaitReason,
    KPROCESSOR_MODE WaitMode,
    BOOLEAN Alertable,
    PLARGE_INTEGER Timeout
    );
```

## -remarks

The current state of the specified *Object* is examined to determine whether the wait can be satisfied immediately. If so, the necessary side effects are performed on the object. Otherwise, the current thread is put in a waiting state and a new thread is selected for execution on the current processor.

The *Alertable* parameter determines when the thread can be alerted and its wait state consequently aborted. For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/waits-and-apcs">Waits and APCs</a>.

A special consideration applies when the *Object* parameter passed to **KeWaitForSingleObject** is a mutex. If the dispatcher object waited on is a mutex, APC delivery is the same as for all other dispatcher objects <u>during the wait</u>. However, after **KeWaitForSingleObject** returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

If the *WaitMode* parameter is **UserMode**, the kernel stack can be swapped out during the wait. Consequently, a caller must <u>never</u> attempt to pass parameters on the stack when calling **KeWaitForSingleObject** using the **UserMode** argument. If you allocate the event on the stack, you must set the *WaitMode* parameter to **KernelMode**.

It is especially important to check the return value of **KeWaitForSingleObject** when the *WaitMode* parameter is **UserMode** or *Alertable* is **TRUE**, because **KeWaitForSingleObject** might return early with a status of STATUS_USER_APC or STATUS_ALERTED.

All long-term waits that can be aborted by a user should be **UserMode** waits and *Alertable* should be set to **FALSE**.

Where possible, *Alertable* should be set to **FALSE** and *WaitMode* should be set to **KernelMode**, in order to reduce driver complexity. The principal exception to this is when the wait is a long-term wait.

If a **NULL** pointer is supplied for *Timeout*, the calling thread remains in a wait state until the *Object* is signaled.

A time-out value of zero allows the testing of a set of wait conditions and for the conditional performance of any side effects if the wait can be immediately satisfied, as in the acquisition of a mutex.

Time-out intervals are measured relative to the system clock, and the accuracy with which the operating system can detect the end of a time-out interval is limited by the granularity of the system clock. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/timer-accuracy">Timer Accuracy</a>.

A mutex can be recursively acquired only MINLONG times. If this limit is exceeded, the routine raises a STATUS_MUTANT_LIMIT_EXCEEDED exception.

Callers of **KeWaitForSingleObject** must be running at IRQL <= DISPATCH_LEVEL. However, if *Timeout* = **NULL** or **Timeout* != 0, the caller must be running at IRQL <= APC_LEVEL and in a nonarbitrary thread context. (If *Timeout* != **NULL** and **Timeout* = 0, the caller must be running at IRQL <= DISPATCH_LEVEL.)

**KeWaitForMutexObject** is a macro that converts to **KeWaitForSingleObject**, which can be used instead.

For better performance, use fast mutexes or guarded mutexes. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/alternatives-to-mutex-objects">Alternatives to Mutex Objects</a>.

For more information about mutex objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mutex-objects">Mutex Objects</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializefastmutex">ExInitializeFastMutex</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kebugcheckex">KeBugCheckEx</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializemutex">KeInitializeMutex</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializesemaphore">KeInitializeSemaphore</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimer">KeInitializeTimer</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>

