---
UID: NF:wdm.ObReferenceObjectWithTag
title: ObReferenceObjectWithTag macro (wdm.h)
description: The ObReferenceObjectWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obreferenceobjectwithtag.htm
tech.root: kernel
ms.assetid: d2b95301-c018-4a2f-801d-a78b00c8d9ca
ms.date: 04/30/2018
ms.keywords: ObReferenceObjectWithTag, ObReferenceObjectWithTag routine [Kernel-Mode Driver Architecture], k107_a35c78fa-edf5-4a93-908b-baf16718b095.xml, kernel.obreferenceobjectwithtag, wdm/ObReferenceObjectWithTag
ms.topic: macro
f1_keywords:
 - "wdm/ObReferenceObjectWithTag"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ObReferenceObjectWithTag
product:
- Windows
targetos: Windows
req.typenames: 
---

# ObReferenceObjectWithTag macro


## -description


The <b>ObReferenceObjectWithTag</b> routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support <a href="https://go.microsoft.com/fwlink/p/?linkid=153590">object reference tracing</a>.


## -parameters




### -param Object [in]

A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a> routine after it opens the object.


### -param Tag [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section.

## -returns
**ObReferenceObjectWithTag** returns a value that is reserved for system use. Drivers must treat this value as VOID.


## -remarks



<b>ObReferenceObjectWithTag</b> simply increments the pointer reference count for an object, without making any access checks on the specified object. In contrast, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbypointerwithtag">ObReferenceObjectByPointerWithTag</a> routines verify that the caller has the required access rights to the object and fail if the caller does not have these rights.

A <b>ObReferenceObjectWithTag</b> call prevents deletion of the specified object at least until the driver either calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a> routine, or closes the object. After the object is no longer needed, the driver must call <b>ObDereferenceObjectWithTag</b> to remove its reference to the object.

When the reference count for an object reaches zero, a kernel-mode component can delete the object. However, a driver can delete only those objects that it created, and a driver should never attempt to delete any object that it did not create.

For more information about object references, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/life-cycle-of-an-object">Life Cycle of an Object</a>.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obfreferenceobject">ObReferenceObject</a> routine is similar to <b>ObReferenceObjectWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObReferenceObject</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObReferenceObject</b> has the same effect as a call to <b>ObReferenceObjectWithTag</b> that specifies <i>Tag</i> = 'tlfD'.

To view an object reference trace in the <a href="https://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-obtrace">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-obtrace">!obtrace</a> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="https://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-reference-tracing-with-tags">Object Reference Tracing with Tags</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obdereferenceobjectwithtag">ObDereferenceObjectWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obfreferenceobject">ObReferenceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbyhandlewithtag">ObReferenceObjectByHandleWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbypointerwithtag">ObReferenceObjectByPointerWithTag</a>
 

 

