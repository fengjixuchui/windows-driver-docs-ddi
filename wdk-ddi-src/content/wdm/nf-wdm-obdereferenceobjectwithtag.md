---
UID: NF:wdm.ObDereferenceObjectWithTag
title: ObDereferenceObjectWithTag macro (wdm.h)
description: The ObDereferenceObjectWithTag routine decrements the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obdereferenceobjectwithtag.htm
tech.root: kernel
ms.assetid: 872098c1-d684-4ce5-9f53-2fee8b50b626
ms.date: 04/30/2018
keywords: ["ObDereferenceObjectWithTag macro"]
ms.keywords: ObDereferenceObjectWithTag, ObDereferenceObjectWithTag routine [Kernel-Mode Driver Architecture], k107_4a4d8579-6641-4d2a-9599-9ac39c25fd91.xml, kernel.obdereferenceobjectwithtag, wdm/ObDereferenceObjectWithTag
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ObDereferenceObjectWithTag
 - wdm/ObDereferenceObjectWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObDereferenceObjectWithTag
---

# ObDereferenceObjectWithTag macro


## -description

The <b>ObDereferenceObjectWithTag</b> routine decrements the reference count of the specified object, and writes a four-byte tag value to the object to support <a href="https://go.microsoft.com/fwlink/p/?linkid=153590">object reference tracing</a>.

## -parameters

### -param Object 

[in]
A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a> routine after it opens the object.

### -param Tag 

[in]
Specifies a four-byte, custom tag value. For more information, see the following Remarks section.

## -remarks

**ObDereferenceObjectWithTag** returns a value that is reserved for system use. Drivers must treat this value as VOID. 






A kernel-mode driver calls this routine to decrement the reference count of an object by one. If the object was created as <i>temporary</i> (that is, the OBJ_PERMANENT flag was not specified when the object was created), and the reference count reaches zero, the object manager deletes the object.

When the reference count for an object reaches zero, a kernel-mode component can delete the object. However, a driver can delete only those objects that it created, and a driver should never attempt to delete any object that it did not create.

An object is <i>permanent</i> if it was created with the OBJ_PERMANENT object attribute flag specified. (For more information about object attributes, see <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>.) A permanent object is created with an initial reference count of one, so the object is not deleted when the driver removes its last reference to the object.

To prepare a permanent object to be deleted, a driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwmaketemporaryobject">ZwMakeTemporaryObject</a> routine to make the object temporary. A driver should only delete a permanent object that it created. Use the following steps to delete a permanent object:

<ol>
<li>
Call <b>ObDereferenceObjectWithTag</b>. 

</li>
<li>
Get the handle to the object. If necessary, call the appropriate <b>ZwOpen<i>Xxx</i></b> or <b>ZwCreate<i>Xxx</i></b> routine to get the object handle.

</li>
<li>
Call <b>ZwMakeTemporaryObject</b> with the handle obtained in step 2. 

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> with the handle obtained in step 2.

</li>
</ol>
If the immediate deletion of an object by the current thread might cause a deadlock, do not call <b>ObDereferenceObjectWithTag</b> to dereference the object. Instead, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdeletewithtag">ObDereferenceObjectDeferDeleteWithTag</a> routine to dereference the object.

For example, such a deadlock can occur if <b>ObDereferenceObjectWithTag</b> is used to dereference a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/windows-kernel-mode-kernel-transaction-manager">Kernel Transaction Manager</a> (KTM) object when a higher-level driver on the driver stack is holding a lock.

For more information about object references, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/life-cycle-of-an-object">Life Cycle of an Object</a>.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> routine is similar to <b>ObDereferenceObjectWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObDereferenceObject</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObDereferenceObject</b> has the same effect as a call to <b>ObDereferenceObjectWithTag</b> that specifies <i>Tag</i> = 'tlfD'.

To view an object reference trace in the <a href="https://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-obtrace">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <b>!obtrace</b> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="https://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-reference-tracing-with-tags">Object Reference Tracing with Tags</a>.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer">IoGetDeviceObjectPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdeletewithtag">ObDereferenceObjectDeferDeleteWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwmaketemporaryobject">ZwMakeTemporaryObject</a>

