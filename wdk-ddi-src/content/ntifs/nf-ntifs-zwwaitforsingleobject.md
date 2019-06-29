---
UID: NF:ntifs.ZwWaitForSingleObject
title: ZwWaitForSingleObject function (ntifs.h)
description: The ZwWaitForSingleObject routine waits until the specified object attains a state of Signaled. An optional time-out can also be specified.
old-location: kernel\zwwaitforsingleobject.htm
tech.root: kernel
ms.assetid: 5eea0877-329d-4fa3-847e-365d6a545b07
ms.date: 04/30/2018
ms.keywords: NtWaitForSingleObject, ZwWaitForSingleObject, ZwWaitForSingleObject routine [Kernel-Mode Driver Architecture], k111_44a7540a-fbf5-4f2e-92d1-0d23cc41a081.xml, kernel.zwwaitforsingleobject, ntifs/NtWaitForSingleObject, ntifs/ZwWaitForSingleObject
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs, SpNoWait
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwWaitForSingleObject
- NtWaitForSingleObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwWaitForSingleObject function


## -description


The <b>ZwWaitForSingleObject</b> routine waits until the specified object attains a state of Signaled. An optional time-out can also be specified.


## -parameters




### -param Handle [in]

A handle to the object.


### -param Alertable [in]

A boolean value that specifies whether the wait is alertable.


### -param Timeout [in, optional]

An optional pointer to a time-out value that specifies the absolute or relative time at which the wait is to be completed. A negative value specifies an interval relative to the current time. The value should be expressed in units of 100 nanoseconds. Absolute expiration times track any changes in the system time. Relative expiration times are not affected by system time changes.


## -returns



<b>ZwWaitForSingleObject</b> can return one of the following possible status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not have the required privileges to the event specified by the <i>Handle</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ALERTED</b></dt>
</dl>
</td>
<td width="60%">
The wait was aborted to deliver an alert to the current thread.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The supplied <i>Handle</i> parameter was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The specified object satisfied the wait.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
A time-out occurred before the object was set to a signaled state. This value can be returned when the specified set of wait conditions cannot be immediately met and the <i>Timeout</i> parameter is set to zero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_USER_APC</b></dt>
</dl>
</td>
<td width="60%">
The wait was aborted to deliver a user APC to the current thread.

</td>
</tr>
</table>
 

Note that the NT_SUCCESS macro recognizes the STATUS_ALERTED, STATUS_SUCCESS, STATUS_TIMEOUT, and STATUS_USER_APC status values as "success" values.




## -remarks



<b>ZwWaitForSingleObject</b> waits until the specified object attains a state of Signaled. An optional timeout can also be specified. <b>ZwWaitForSingleObject</b> examines the current state of the specified object to determine whether the wait can be satisfied immediately. If so, actions are performed. Otherwise, the current thread is put in a waiting state and a new thread is selected for execution on the current processor.

If a <i>Timeout</i> parameter is not specified, then the wait will not be satisfied until the object attains a state of Signaled. If a <i>Timeout</i> parameter is specified, and the object has not attained a state of Signaled when the time-out expires, then the wait is automatically satisfied. If an explicit <i>Timeout</i> value of zero is specified, then no wait will occur if the wait cannot be satisfied immediately. A <i>Timeout</i> value of zero allows the testing of a set of wait conditions and for the conditional performance of any side effects if the wait can be immediately satisfied, as in the acquisition of a mutex. The wait can also be specified as alertable.

The <i>Alertable</i> parameter specifies whether the thread can be alerted and its wait state consequently aborted. If the value of this parameter is <b>FALSE</b> then the thread cannot be alerted. The only exception to this rule is that of a terminating thread. Under certain circumstances a terminating thread can be alerted while it is in the process of winding down. A thread is automatically made alertable, for instance, when terminated by a user with a CTRL+C.

If the value of <i>Alertable</i>is <b>TRUE</b> and one of the following conditions is present, the thread will be alerted:

<ol>
<li>
If the origin of the alert is an internal, undocumented kernel-mode routine used to alert threads.

</li>
<li>
The origin of the alert is a user-mode APC.

</li>
</ol>
In the first of these two cases, the thread's wait is satisfied with a completion status of STATUS_ALERTED. In the second case, it is satisfied with a completion status of STATUS_USER_APC.

The thread must be alertable for a user-mode APC to be delivered. This is not the case for kernel-mode APCs. A kernel-mode APC can be delivered and executed even though the thread is not alerted. Once the APC's execution completes, the thread's wait resumes. A thread is never alerted, nor is its wait aborted, by the delivery of a kernel-mode APC.

The delivery of kernel-mode APCs to a waiting thread does not depend on whether the thread can be alerted. If the kernel-mode APC is a special kernel-mode APC, then the APC is delivered provided that the IRQL is less than APC_LEVEL. If the kernel-mode APC is a normal kernel-mode APC, then the APC is delivered provided that the following three conditions hold: (1) the IRQL is less than APC_LEVEL, (2) no kernel APC is in progress, and (3) the thread is not in a critical section.

If the handle passed to <b>ZwWaitForSingleObject</b> refers to a mutex, the APC delivery is the same as for all other dispatcher objects during the wait. However, once <b>ZwWaitForSingleObject</b> returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

It is especially important to check the return value of <b>ZwWaitForSingleObject</b> when the <i>Alertable</i> parameter is <b>TRUE</b>, because <b>ZwWaitForSingleObject</b> might return early with a status of STATUS_USER_APC or STATUS_ALERTED.

All long term waits can be aborted by a user if the <i>Alertable</i> parameter is set to <b>FALSE</b>.

For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/waits-and-apcs">Do Waiting Threads Receive Alerts and APCs?</a>


Callers of <b>ZwWaitForSingleObject</b> must be running at IRQL less than or equal to DISPATCH_LEVEL. Usually, the caller must be running at IRQL PASSIVE_LEVEL and in a nonarbitrary thread context. A call while running at IRQL DISPATCH_LEVEL is valid if and only if the caller specifies a <i>Timeout</i> parameter of zero. That is, a driver must not wait for a nonzero interval at IRQL equal to DISPATCH_LEVEL.

Time-out intervals are measured relative to the system clock, and the accuracy of the time-out measurement is limited by the granularity of the system clock. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/timer-accuracy">Timer Accuracy</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwWaitForSingleObject</b> function occurs in user mode, you should use the name "<b>NtWaitForSingleObject</b>" instead of "<b>ZwWaitForSingleObject</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocreatenotificationevent">IoCreateNotificationEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocreatesynchronizationevent">IoCreateSynchronizationEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keclearevent">KeClearEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keresetevent">KeResetEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesetevent">KeSetEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566423">ZwCreateEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567092">ZwSetEvent</a>
 

 

