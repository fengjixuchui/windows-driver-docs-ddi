---
UID: NF:wdm.ObDereferenceObject
title: ObDereferenceObject macro (wdm.h)
description: The ObDereferenceObject routine decrements the given object's reference count and performs retention checks.
old-location: kernel\obdereferenceobject.htm
tech.root: kernel
ms.assetid: 8cd2d7ae-ebbe-41c6-8773-7a517bc6f714
ms.date: 04/30/2018
keywords: ["ObDereferenceObject macro"]
ms.keywords: ObDereferenceObject, ObDereferenceObject routine [Kernel-Mode Driver Architecture], k107_bc67abd9-66b2-4cd7-81c0-48ad0fa6c87d.xml, kernel.obdereferenceobject, wdm/ObDereferenceObject
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
 - ObDereferenceObject
 - wdm/ObDereferenceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObDereferenceObject
---

# ObDereferenceObject macro


## -description

The <b>ObDereferenceObject</b> routine decrements the given object's reference count and performs retention checks.

## -parameters

### -param a 

[in]
Pointer to the object's body.

## -remarks

**ObDereferenceObject** returns a value that is reserved for system use. Drivers must treat this value as VOID.


<b>ObDereferenceObject</b> decreases the reference count of an object by one. If the object was created as temporary (the OBJ_PERMANENT flag was not specified on creation), and the reference count reaches zero, the object can be deleted by the system.

A driver can delete a temporary object it created by decreasing its reference count to zero. A driver must never attempt to delete an object it did not create.

An object is permanent if it was created with the OBJ_PERMANENT object attribute flag specified. (For more information about object attributes, see <a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>.) A permanent object is created with a reference count of one, so it is not deleted when the driver dereferences it. A driver can only delete a permanent object it created by using the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwmaketemporaryobject">ZwMakeTemporaryObject</a> routine to make it temporary. Use the following steps to delete a permanent object that you created:

<ol>
<li>
Call <b>ObDereferenceObject</b>.

</li>
<li>
Call the appropriate <b>ZwOpen<i>Xxx</i></b> or <b>ZwCreate<i>Xxx</i></b> routine to get a handle for the object, if necessary.

</li>
<li>
Call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwmaketemporaryobject">ZwMakeTemporaryObject</a> with the handle obtained in step 2.

</li>
<li>
Call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> with the handle obtained in step 2.

</li>
</ol>
<div class="alert"><b>Important</b>  
     Use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdelete">ObDereferenceObjectDeferDelete</a> instead of <b>ObDereferenceObject</b> for any object, particularly <a href="/windows-hardware/drivers/kernel/windows-kernel-mode-kernel-transaction-manager">Kernel Transaction Manager</a> (KTM) objects, when the immediate deletion by the current thread of the object (by using <b>ObDereferenceObject</b>) might result in a deadlock.</div>
<div> </div>

## -see-also

<a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer">IoGetDeviceObjectPointer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobjectdeferdelete">ObDereferenceObjectDeferDelete</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwmaketemporaryobject">ZwMakeTemporaryObject</a>