---
UID: NF:fltkernel.FltCancellableWaitForSingleObject
title: FltCancellableWaitForSingleObject function (fltkernel.h)
description: The FltCancellableWaitForSingleObject routine executes a cancelable wait operation (a wait that can be terminated) on a dispatcher object.
old-location: ifsk\fltcancellablewaitforsingleobject.htm
tech.root: ifsk
ms.assetid: bf872769-c084-44c9-97e8-58eb54f943b2
ms.date: 04/16/2018
keywords: ["FltCancellableWaitForSingleObject function"]
ms.keywords: FltApiRef_a_to_d_e71d2b38-ae04-4026-bb99-d0d99ea4ec05.xml, FltCancellableWaitForSingleObject, FltCancellableWaitForSingleObject routine [Installable File System Drivers], fltkernel/FltCancellableWaitForSingleObject, ifsk.fltcancellablewaitforsingleobject
f1_keywords:
 - "fltkernel/FltCancellableWaitForSingleObject"
 - "FltCancellableWaitForSingleObject"
req.header: fltkernel.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available in Microsoft Windows Vista and later version of Windows operating systems.
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
req.dll: Fltmgr.sys
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
- wdfilter.sys
api_name:
- FltCancellableWaitForSingleObject
targetos: Windows
req.typenames: 
---

# FltCancellableWaitForSingleObject function


## -description


The <b>FltCancellableWaitForSingleObject</b> routine executes a cancelable wait operation (a wait that can be terminated) on a dispatcher object.


## -parameters




### -param Object [in]

A pointer to an initialized dispatcher object (event, mutex, semaphore, thread, or timer) for which the caller supplies the storage. 


### -param Timeout [in, optional]

A pointer to an optional time-out value. This parameter specifies the absolute or relative time, in 100 nanosecond units, when the wait is to be completed. 

If <i>Timeout</i> points to a zero value (that is, *<i>Timeout</i> == 0), the routine returns without waiting. If the caller supplies a <b>NULL</b> pointer (that is, <i>Timeout</i> == <b>NULL</b>), the routine waits indefinitely until the object is set to the signaled state. 

A positive <i>Timeout</i> value specifies an absolute time, relative to January 1, 1601. A negative <i>Timeout</i> value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time. Relative expiration times are not affected by system time changes.

If <i>Timeout</i> is specified, the wait is automatically satisfied if the object is not set to the signaled state when the given interval expires.

A time-out value of zero (that is, *<i>Timeout</i> == 0) allows you to test a set of wait conditions, and to conditionally perform any additional actions if the wait can be immediately satisfied, as in the acquisition of a mutex. 


### -param CallbackData [in, optional]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> structure that represents the I/O operation that was issued by the user and that can be canceled by the user. The caller must ensure that the I/O operation will remain valid for the duration of this routine and that the I/O must not have a cancel routine set (for example, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcancelcompletion">FltSetCancelCompletion</a> function must not have been called on the I/O operation). Note that the caller must hold the<i>CallbackData</i>; it cannot be passed to a lower-level driver. 


## -returns



<b>FltCancellableWaitForSingleObject</b> can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS </b></dt>
</dl>
</td>
<td width="60%">
The dispatcher object that is specified by the <i>Object</i> parameter has been set to the signaled state.. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TIMEOUT </b></dt>
</dl>
</td>
<td width="60%">
A time-out occurred before the object was set to a signaled state. This value can also be returned when the specified wait condition cannot be immediately met and <i>Timeout</i> is set to zero. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ABANDONED_WAIT_0 </b></dt>
</dl>
</td>
<td width="60%">
The caller attempted to wait for a mutex that has been abandoned. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED </b></dt>
</dl>
</td>
<td width="60%">
The wait was interrupted by a pending cancel request on the I/O operation. Note that this value is returned only if <i>CallbackData</i> corresponds to an IRP based operation is passed to <b>FltCancellableWaitForSingleObject</b> and the I/O was canceled by a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_THREAD_IS_TERMINATING </b></dt>
</dl>
</td>
<td width="60%">
The wait was interrupted because the application or user has terminated the thread. 

</td>
</tr>
</table>
 

The return value only indicates the status of the wait. 



Note that the NT_SUCCESS macro returns <b>FALSE</b> ("failure") for the STATUS_CANCELLED and STATUS_THREAD_IS_TERMINATING status values and <b>TRUE</b> ("success") for all other status values.




## -remarks



The <b>FltCancellableWaitForSingleObject</b> routine executes a cancelable wait operation on a dispatcher object. If the user or application terminates the thread, or if an I/O associated with the thread was canceled by a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>, the wait is canceled.

The routine is designed to support the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/design/dn613954(v=vs.85)">I/O Completion/Cancellation Guidelines</a>. The goal of these guidelines is to allow users to quickly terminate applications. This, in turn, requires that applications have the ability to quickly terminate threads that are executing I/O and any current I/O operations. This routine provides a way for user threads to block (that is, wait) in the kernel for I/O completion, dispatcher objects, or synchronization variables in a way that allows the wait to be readily canceled. This routine also permits the thread's wait to be terminated if the thread is terminated by a user or an application.

For example, a redirector may need to create a secondary I/O operation in order to process a user-mode I/O and synchronously wait for the secondary request to complete. One way to do this is to set up an event that will be signaled by the completion routine of the secondary I/O operation and then wait for the event to be signaled. Then, to perform a cancelable wait operation, <b>FltCancellableWaitForSingleObject</b> is called passing in the event associated with the secondary I/O operation, and the original user-mode I/O operation. The thread's wait for the event to be signaled is canceled if a pending termination event occurs or if the original user-mode I/O operation is canceled.

Note that terminating the wait does not automatically cancel any I/O operation that was issued by the caller - that must be handled separately by the caller.

A special consideration applies when the <i>Object</i> parameter passed to <b>FltCancellableWaitForSingleObject</b> is a mutex. If the dispatcher object that is waited on is a mutex, APC delivery is the same as for all other dispatcher objects during the wait. However, once <b>FltCancellableWaitForSingleObject</b> returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

A mutex can be recursively acquired only MINLONG times. If this limit is exceeded, the routine raises a STATUS_MUTANT_LIMIT_EXCEEDED exception.

<b>FltCancellableWaitForSingleObject</b> must be called at IRQL PASSIVE_LEVEL if the <i>CallbackData</i> parameter represents a valid filter manager IRP. Otherwise, the routine can be called at IRQL less or equal to APC_LEVEL. Normal kernel APCs can be disabled by the caller, if needed, by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsrtlenterfilesystem">FsRtlEnterFileSystem</a> routines. However, special kernel APCs must not be disabled. 

The <b>FltCancellableWaitForSingleObject</b> routine will assert on debug builds if the <i>CallbackData</i> represents a Filter Manager IRP operation, but the IRP in the <i>CallbackData</i> structure is <b>NULL</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializefastmutex">ExInitializeFastMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancellablewaitformultipleobjects">FltCancellableWaitForMultipleObjects</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcancelcompletion">FltSetCancelCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545738">FsRtlCancellableWaitForSingleObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializemutex">KeInitializeMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializesemaphore">KeInitializeSemaphore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimer">KeInitializeTimer</a>



<b>KeWaitForMultipleObjects</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
 

 

