---
UID: NF:fltkernel.FltCancellableWaitForMultipleObjects
title: FltCancellableWaitForMultipleObjects function (fltkernel.h)
description: The FltCancellableWaitForMultipleObjects executes a cancelable wait operation (a wait that can be terminated) on one or more dispatcher objects.
old-location: ifsk\fltcancellablewaitformultipleobjects.htm
tech.root: ifsk
ms.assetid: 0afe431d-55dd-4aaa-bcbc-467ac3a7b604
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_3f130d06-8af0-46c1-9db3-bd70d1cbabe1.xml, FltCancellableWaitForMultipleObjects, FltCancellableWaitForMultipleObjects function [Installable File System Drivers], ifsk.fltcancellablewaitformultipleobjects, ntifs/FltCancellableWaitForMultipleObjects
ms.topic: function
req.header: fltkernel.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows Vista and later versions of Windows operating systems.
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
req.lib: Fltmgr.lib
req.dll: 
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fltmgr.lib
- fltmgr.dll
api_name:
- FltCancellableWaitForMultipleObjects
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCancellableWaitForMultipleObjects function


## -description


The <b>FltCancellableWaitForMultipleObjects</b> executes a cancelable wait operation (a wait that can be terminated) on one or more dispatcher objects.


## -parameters




### -param Count [in]

The number of objects to be waited on.


### -param ObjectArray [in]

A pointer to an array of pointers to dispatcher objects (events, mutexes, semaphores, threads, and timers) for which the caller supplies the storage.


### -param WaitType [in]

An enumumeration with the value of either <b>WaitAll</b>, which indicates that all of the specified objects must attain a signaled state before the wait is satisfied; or <b>WaitAny</b>, which indicates that any one of the objects must attain a signaled state before the wait is satisfied. 


### -param Timeout [in, optional]

A pointer to an optional time-out value. This parameter specifies the absolute or relative time in 100 nanosecond units at which the wait is to be completed.

If Timeout points to a zero value (that is, *Timeout == 0), the routine returns without waiting. If the caller supplies a <b>NULL</b> pointer (that is, Timeout == <b>NULL</b>), the routine waits indefinitely until any or all of the dispatcher objects are set to the signaled state.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes. 

If Timeout is specified, the wait is automatically satisfied if none of the specified wait conditions are met when the given interval expires.

A time-out value of zero (that is, *Timeout == 0) allows you to test a set of wait conditions, and to conditionally perform any additional actions if the wait can be immediately satisfied, as in the acquisition of a mutex. 


### -param WaitBlockArray [in, optional]

If Count <= THREAD_WAIT_OBJECTS, WaitBlockArray can be <b>NULL</b>. Otherwise, this parameter must point to a memory buffer of <code>sizeof(KWAIT_BLOCK) * Count</code> bytes. The routine uses this buffer for record-keeping while performing the wait operation. 


### -param CallbackData [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure that represents the I/O operation that was issued by the user and that can be canceled by the user. The caller must ensure that the I/O operation will remain valid for the duration of this routine and that the I/O must not have a cancel routine set (for example, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetcancelcompletion">FltSetCancelCompletion</a> function must not have been called on the I/O operation). Note that the <i>CallbackData</i> must be held by the caller as it cannot be passed to a lower-level driver. 


## -returns



<b>FltCancellableWaitForMultipleObjects</b> can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The caller specified <b>WaitAll</b> for the <i>WaitType</i> parameter and all dispatcher objects in the <i>ObjectArray</i> array have been set to the signaled state. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
A time-out occurred before the specified set of wait conditions was met. This value can also be returned when the specified set of wait conditions cannot be immediately met and Timeout is set to zero. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WAIT_0 through STATUS_WAIT_63</b></dt>
</dl>
</td>
<td width="60%">
The caller specified <b>WaitAny</b> for <i>WaitType</i> and one of the dispatcher objects in the <i>ObjectArray</i> array has been set to the signaled state. The lower six bits of the return value encode the zero-based index of the object that satisfied the wait. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ABANDONED_WAIT_0 through STATUS_ABANDONED_WAIT_63</b></dt>
</dl>
</td>
<td width="60%">
The caller attempted to wait for a mutex that has been abandoned. The lower six bits of the return value encode the zero-based index of the mutex in the <i>ObjectArray</i> array. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The wait was interrupted by a pending cancel request on the I/O operation. Note that this value is returned only if <i>CallbackData</i> that corresponds to an IRP based operation is passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcancellablewaitformultipleobjects">FltCancellableWaitForMultipleObjects</a> and the I/O was canceled by a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_THREAD_IS_TERMINATING</b></dt>
</dl>
</td>
<td width="60%">
The wait was interrupted because an application or the user has terminated the thread.

</td>
</tr>
</table>
 

The return value only indicates the status of the wait. 

Note that the NT_SUCCESS macro returns <b>FALSE</b> ("failure") for the STATUS_CANCELLED and STATUS_THREAD_IS_TERMINATING status values and <b>TRUE</b> ("success") for all other status values.




## -remarks



The <b>FltCancellableWaitForMultipleObjects</b> executes a cancelable wait operation on dispatcher objects. If the user or the application terminates the thread, or if an I/O operation associated with the thread was canceled by a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>, the wait is canceled.

The routine is designed to support the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/design/dn613954(v=vs.85)">I/O Completion/Cancellation Guidelines</a>. The goal of these guidelines is to allow users to quickly terminate applications. This, in turn, requires that applications have the ability to quickly terminate threads that are executing I/O and any current I/O operations. This routine provides a way for user threads to block (that is, wait) in the kernel for I/O completion, dispatcher objects, or synchronization variables in a way that allows the wait to be readily canceled. This routine also permits the thread's wait to be terminated if the thread is terminated by a user or an application.

For example, a redirector may need to create one or more secondary I/O operations in order to process a user-mode I/O and synchronously wait for the secondary requests to complete. One way to do this is to set up an event that will be signaled by the completion routine of the secondary I/O operations and then wait for the event to be signaled. Then, to perform a cancelable wait operation, <b>FltCancellableWaitForMultipleObjects</b> is called passing in the events associated with the secondary I/O operations, and the original user-mode I/O operation. The thread's wait for the event to be signaled is canceled if a pending termination event occurs or if the original user-mode I/O operation is canceled.

Note that terminating the wait does not automatically cancel any I/O operation that was issued by the caller - that must be handled separately by the caller.

Each thread object has a built-in array of wait blocks that you can use to wait on several objects concurrently. Whenever possible, you should use the built-in array of wait blocks in a wait-multiple operation because no additional wait block storage needs to be allocated and later deallocated. However, if the number of objects that you must wait on concurrently is greater than the number of built-in wait blocks, use the <i>WaitBlockArray</i> parameter to specify an alternate set of wait blocks to be used in the wait operation. Drivers only need to allocate a sufficiently-large memory buffer for <i>WaitBlockArray</i>. You do not need to initialize the buffer, and the drivers can treat it as an opaque structure. You can free the buffer once the routine returns.

If either Count is greater than MAXIMUM_WAIT_OBJECTS or if <i>WaitBlockArray</i> is <b>NULL</b> and Count is greater than THREAD_WAIT_OBJECTS, the system issues <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0xc--maximum-wait-objects-exceeded">Bug Check 0xC: MAXIMUM_WAIT_OBJECTS_EXCEEDED</a>.

A special consideration applies when one or more of the elements in the <i>ObjectArray</i> parameter passed to <b>FltCancellableWaitForMultipleObjects</b> refers to a mutex. If the dispatcher object that is waited on is a mutex, APC delivery is the same as for all other dispatcher objects during the wait. However, once <b>FltCancellableWaitForMultipleObjects</b> returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

A mutex can be recursively acquired only MINLONG times. If this limit is exceeded, the routine raises a STATUS_MUTANT_LIMIT_EXCEEDED exception. 

The <b>FltCancellableWaitForMultipleObjects</b> routine must be called at IRQL PASSIVE_LEVEL if the <i>CallbackData</i> parameter represents a valid filter manager IRP. Otherwise, the routine can be called at IRQL less or equal to APC_LEVEL. Normal kernel APCs can be disabled by the caller, if needed, by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsrtlenterfilesystem">FsRtlEnterFileSystem</a> routines. However, special kernel APCs must not be disabled. 

<b>FltCancellableWaitForMultipleObjects</b> will assert on debug builds if the <i>CallbackData</i> represents a Filter Manager IRP operation, but the IRP in the <i>CallbackData</i> structure is <b>NULL</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exinitializefastmutex">ExInitializeFastMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcancellablewaitforsingleobject">FltCancellableWaitForSingleObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetcancelcompletion">FltSetCancelCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545731">FsRtlCancellableWaitForMultipleObjects</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializemutex">KeInitializeMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializesemaphore">KeInitializeSemaphore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializetimer">KeInitializeTimer</a>



<b>KeWaitForMultipleObjects</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
 

 

