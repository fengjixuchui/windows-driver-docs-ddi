---
UID: NF:wdfsync.WdfWaitLockAcquire
title: WdfWaitLockAcquire function (wdfsync.h)
description: The WdfWaitLockAcquire method acquires a specified wait lock.
old-location: wdf\wdfwaitlockacquire.htm
tech.root: wdf
ms.assetid: 6fe7465d-938a-400f-b141-76e8a5ffbe90
ms.date: 02/26/2018
keywords: ["WdfWaitLockAcquire function"]
ms.keywords: DFSynchroRef_eccb7d51-5e5e-4b2b-8156-c22d35f46809.xml, WdfWaitLockAcquire, WdfWaitLockAcquire method, kmdf.wdfwaitlockacquire, wdf.wdfwaitlockacquire, wdfsync/WdfWaitLockAcquire
f1_keywords:
 - "wdfsync/WdfWaitLockAcquire"
req.header: wdfsync.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, WdfWaitlock, WdfWaitlockRelease
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfWaitLockAcquire
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWaitLockAcquire function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfWaitLockAcquire</b> method acquires a specified wait lock.


## -parameters




### -param Lock [in]

A handle to a framework wait-lock object, obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfwaitlockcreate">WdfWaitLockCreate</a>.


### -param Timeout [in, optional]

An optional pointer to a time-out value. The time-out value is specified in system time units (100-nanosecond intervals).

 If the pointer is non-<b>NULL</b>, the framework cancels the attempt to obtain the lock if it is not completed within the specified time-out period. Time-out values can be negative, positive, or zero, as follows:

<ul>
<li>
If the time-out value is negative, the expiration time is relative to the current system time.

</li>
<li>
If the time-out value is positive, the expiration time is specified as an absolute time (which is actually relative to January 1, 1601). 

</li>
<li>
If the time-out value is zero, <b>WdfWaitLockAcquire</b> attempts to acquire the lock and then returns immediately, whether it has acquired the lock or not. 

</li>
</ul>
Relative expiration times are not affected by any changes to the system time that might occur within the specified time-out period. Absolute expiration times do reflect system time changes.

The framework provides <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftimer/">time conversion functions</a> that convert time values into system time units.

If the caller supplies a <b>NULL</b> pointer, the method waits indefinitely until it has acquired the lock.


## -returns



<b>WdfWaitLockAcquire</b> can return the following <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>:

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
The caller has acquired the wait lock.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Timeout</i> interval expired before the lock was acquired.

</td>
</tr>
</table>
 

Note that <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(status) equals <b>TRUE</b> for all of these status values.



The caller does not have to check the return value if the <i>Timeout</i> pointer is <b>NULL</b>, because in that case <b>WdfWaitLockAcquire</b> returns only after it acquires the lock.



A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfWaitLockAcquire</b> method does not return until it acquires the wait lock or until the time-out period expires. 

<b>WdfWaitLockAcquire</b> calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a> before acquiring the wait lock.  As a result, when the method returns, <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/types-of-apcs">normal kernel APCs</a> are disabled. <b>WdfWaitLockAcquire</b> does not alter the caller's IRQL.

If the <i>Timeout</i> pointer is <b>NULL</b>, or if the time-out value is not zero, <b>WdfWaitLockAcquire</b> must be called at IRQL = PASSIVE_LEVEL.

If the time-out value is zero, <b>WdfWaitLockAcquire</b> must be called at IRQL < DISPATCH_LEVEL. Note that this is in disagreement with the header file (wdfsync.h), which indicates that this method can be called at DISPATCH_LEVEL.

For more information about wait locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.


#### Examples

The following code example acquires a wait lock, adds a device object to an object collection, and releases the wait lock.

```cpp
WdfWaitLockAcquire(
                   FilterDeviceCollectionLock,
                   NULL
                   );
status = WdfCollectionAdd(
                          FilterDeviceCollection,
                          deviceHandle
                          );
if (!NT_SUCCESS(status)) {
    addFailed = TRUE;
}
WdfWaitLockRelease(FilterDeviceCollectionLock);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfsync/nf-wdfsync-wdfwaitlockcreate">WdfWaitLockCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/kmdf-wdfwaitlockrelease">WdfWaitLockRelease</a>
 

 

