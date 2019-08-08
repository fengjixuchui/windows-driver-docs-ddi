---
UID: NF:wdm.ExSetResourceOwnerPointerEx
title: ExSetResourceOwnerPointerEx function (wdm.h)
description: The ExSetResourceOwnerPointerEx routine transfers the ownership of an executive resource from the calling thread to an owner pointer, which is a system address that identifies the resource owner.
old-location: kernel\exsetresourceownerpointerex.htm
tech.root: kernel
ms.assetid: 96293fbc-0c3c-4685-8708-dd84fcc2223e
ms.date: 04/30/2018
ms.keywords: ExSetResourceOwnerPointerEx, ExSetResourceOwnerPointerEx routine [Kernel-Mode Driver Architecture], k102_2bcc65e9-00e7-4fc5-a1d6-1f797b2c6038.xml, kernel.exsetresourceownerpointerex, wdm/ExSetResourceOwnerPointerEx
ms.topic: function
f1_keywords:
 - "wdm/ExSetResourceOwnerPointerEx"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
- ExSetResourceOwnerPointerEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExSetResourceOwnerPointerEx function


## -description


The <b>ExSetResourceOwnerPointerEx</b> routine transfers the ownership of an executive resource from the calling thread to an owner pointer, which is a system address that identifies the resource owner. 


## -parameters




### -param Resource [in, out]

A pointer to an executive resource (an opaque <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eresource-structures">ERESOURCE</a> structure) that is owned by the calling thread. The caller previously allocated this structure and initialized it by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exinitializeresourcelite">ExInitializeResourceLite</a> routine. For more information, see the following Remarks section. 


### -param OwnerPointer [in]

A pointer value that identifies the resource owner. This parameter value is nominally a pointer to a value of type ERESOURCE_THREAD but is cast to type PVOID. The caller must set the two least significant bits of this pointer value to ones. For more information, see the following Remarks section.


### -param Flags [in]

A set of flags that can modify the operation of this routine. Set this parameter either to zero or to the following flag value:

<ul>
<li>
FLAG_OWNER_POINTER_IS_THREAD

</li>
</ul>
If <i>Flags</i> = FLAG_OWNER_POINTER_IS_THREAD, <i>OwnerPointer</i> must point to a value of type ERESOURCE_THREAD, which is a pointer to an opaque thread object. If <i>Flags</i> = 0, <i>OwnerPointer</i> must point to a storage object in system memory that remains allocated until the resource is released. For more information, see the following Remarks section.


## -returns



None




## -remarks



This routine is available in Windows 7 and later versions of the Windows operating system.

<b>ExSetResourceOwnerPointerEx</b> enables a thread, which acts as a resource manager, to transfer ownership of an executive resource, which the thread has already acquired, to another thread, which then uses the resource. The executive resource is represented by an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eresource-structures">ERESOURCE</a> structure.

The caller must set the two least significant bits of the <i>OwnerPointer</i> parameter value to ones. The operating system uses these bits internally to distinguish an owner pointer that has been set by an <b>ExSetResourceOwnerPointerEx</b> call from a thread that has acquired a resource by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544351">ExAcquireResourceExclusiveLite</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a> routine.

The thread that calls <b>ExSetResourceOwnerPointerEx</b> to transfer ownership of a resource must be the same thread that previously called the <b>ExAcquireResource<i>Xxx</i>Lite</b> routine to acquire the resource.

If the resource-manager thread acquired the resource for exclusive access (by calling <b>ExAcquireResourceExclusiveLite</b>), the <b>ExSetResourceOwnerPointerEx</b> call transfers exclusive-access ownership to the resource-user thread. If the resource-manager thread acquired the resource for shared access (by calling <b>ExAcquireResourceSharedLite</b>), the <b>ExSetResourceOwnerPointerEx</b> call transfers shared-access ownership to the resource-user thread.

When the resource-user thread no longer needs the resource, the resource should be released. Typically, the resource-user thread releases the resource. To do so, it must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545585">ExReleaseResourceForThreadLite</a> routine. In this call, the <i>ThreadId</i> parameter value must match the value of the <i>OwnerPointer</i> parameter (including the two least significant bits) in the previous <b>ExSetResourceOwnerPointerEx</b> call that transferred ownership of the resource.

After a <b>ExSetResourceOwnerPointerEx</b> call transfers ownership of a resource, the only other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-eresource-routines">ERESOURCE routine</a> that a driver can call for the specified resource is <b>ExReleaseResourceForThreadLite</b>. An attempt to call another <b>ERESOURCE</b> routine, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exreleaseresourcelite">ExReleaseResourceLite</a>, for this resource is an error.

<b>ExSetResourceOwnerPointerEx</b> can operate in two significantly different modes. The mode is specified by the <i>Flags</i> parameter. To select the more versatile of the two modes, set <i>Flags</i> = FLAG_OWNER_POINTER_IS_THREAD. This <i>Flags</i> value informs the operating system that the <i>OwnerPointer</i> parameter is a pointer to the thread object of the resource-manager thread. The operating system can, if necessary, use this information to temporarily boost the priority of this thread to avoid priority inversion. To obtain the thread object pointer to use for the <i>OwnerPointer</i> value, a driver can call the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff544614(v=vs.85)">ExGetCurrentResourceThread</a> routine. Remember to set the two least significant bits of the <i>OwnerPointer</i> value to ones.

If <i>Flags</i> is zero, the behavior of <b>ExSetResourceOwnerPointerEx</b> is the same as that of the legacy <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exsetresourceownerpointer">ExSetResourceOwnerPointer</a> routine, which is available in Windows 2000 and later versions of the Windows operating system. That is, the <i>OwnerPointer</i> parameter points to a storage object that the resource-manager thread allocates in system memory before it calls <b>ExSetResourceOwnerPointerEx</b>. In this case, the object type and value are not relevant because <b>ExSetResourceOwnerPointerEx</b> does not attempt to access the object itself. Instead, the routine simply uses the memory address of the object to identify the resource owner. The storage for the object must begin at an even four-byte boundary in memory. To prevent two drivers from inadvertently using the same owner pointer at the same time, the resource-manager thread must not release the storage for the object until the resource is released.

For more information about managing executive resources, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-eresource-routines">Introduction to ERESOURCE Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eresource-structures">ERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544351">ExAcquireResourceExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff544614(v=vs.85)">ExGetCurrentResourceThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exinitializeresourcelite">ExInitializeResourceLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545585">ExReleaseResourceForThreadLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exreleaseresourcelite">ExReleaseResourceLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exsetresourceownerpointer">ExSetResourceOwnerPointer</a>
 

 

