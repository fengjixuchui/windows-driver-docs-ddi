---
UID: NF:ntddk.MmSecureVirtualMemory
title: MmSecureVirtualMemory function (ntddk.h)
description: The MmSecureVirtualMemory routine secures a user-space memory address range so that it cannot be freed and its protection type cannot be made more restrictive.
old-location: kernel\mmsecurevirtualmemory.htm
tech.root: kernel
ms.assetid: e5c2d5d5-550e-42e5-b86a-f17e361925dc
ms.date: 04/30/2018
ms.keywords: MmSecureVirtualMemory, MmSecureVirtualMemory routine [Kernel-Mode Driver Architecture], k106_d85881bb-59a3-4494-afaa-55c49b71b64b.xml, kernel.mmsecurevirtualmemory, ntddk/MmSecureVirtualMemory
ms.topic: function
f1_keywords:
 - "ntddk/MmSecureVirtualMemory"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmSecureVirtualMemory
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: 19H1
---

# MmSecureVirtualMemory function


## -description


The <b>MmSecureVirtualMemory</b> routine secures a user-space memory address range so that it cannot be freed and its page protection cannot be made more restrictive.


## -parameters




### -param Address [in]

The beginning of the user virtual address range to secure.


### -param Size [in]

The size, in bytes, of the virtual address range to secure.


### -param ProbeMode [in]

Specifies the most restrictive page protection that is allowed. Use PAGE_READWRITE to specify that the address range must remain both readable and writable, or use PAGE_READONLY to specify that the address range must only remain readable.

<table>
<tr><th>ProbeMode</th><th>Meaning</th></tr>
<tr><td>PAGE_READWRITE</td><td>Protection cannot be changed to PAGE_NOACCESS or PAGE_READONLY. All other protection changes are allowed.</td></tr>
<tr><td>PAGE_READONLY</td><td>Protection cannot be changed to PAGE_NOACCESS. All other protection changes are allowed.</td></tr>
</table>


## -returns



On success, <b>MmSecureVirtualMemory</b> returns an opaque pointer value that the driver passes to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmunsecurevirtualmemory">MmUnsecureVirtualMemory</a> routine to unsecure the memory address range. If the routine is unable to secure the memory address range, it returns <b>NULL</b>.




## -remarks


<b>MmSecureVirtualMemory</b> can be used to avoid certain race conditions on user-mode buffers. For example, if a driver checks to see if the buffer is writable, but then the originating user-mode process changes the buffer to be read-only before the driver can write to the buffer, then a race condition can result. The driver can use <b>MmSecureVirtualMemory</b> with PAGE_READWRITE probe mode to guarantee that the buffer will remain writable until the driver calls <b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmunsecurevirtualmemory">MmUnsecureVirtualMemory</a></b>. The routine also protects against the originating user-mode process freeing the buffer. Here are a few guidelines about calling these routines:<ul>
<li>
Calling <b>MmSecureVirtualMemory</b> with PAGE_READONLY does not guarantee that the buffer will remain read-only. The read-only probe mode prevents the user from changing the protection of the buffer to PAGE_NOACCESS. It does <i>not</i> prevent changing the protection to PAGE_READWRITE (or PAGE_WRITECOPY, for mapped views).
</li>
<li>
If a driver calls <b>MmSecureVirtualMemory</b> and does not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmunsecurevirtualmemory">MmUnsecureVirtualMemory</a>, the memory is automatically unsecured when the process terminates.

</li>
<li>
If the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmunsecurevirtualmemory">MmUnsecureVirtualMemory</a>, it must call it in the context of the process in which the memory was originally secured, and before that process terminates.

</li>
<li>
Typically drivers need to reference the process when they secure the memory, then later call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-kestackattachprocess">KeStackAttachProcess</a> to switch to the context of that process before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmunsecurevirtualmemory">MmUnsecureVirtualMemory</a>.

</li>
<li>
To detect process termination drivers can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">PsSetCreateProcessNotifyRoutine</a>. Alternatively, the process can submit an IRP with a cancel routine that is invoked by the I/O manager when the process is exiting. In the cancel routine the driver can attach to the process and call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmunsecurevirtualmemory">MmUnsecureVirtualMemory</a>.

</li>
</ul>


While <b>MmSecureVirtualMemory</b> can be used to guarantee that reading or writing user memory will not raise an exception due to insufficient page permissions, it does not protect against other types of exceptions. For example, it does not protect against exceptions raised when the system finds a bad disk block in the page file. Therefore, drivers must still wrap all user memory accesses in a <b>try/except</b> block. Because of this, we recommend that drivers do not use this function. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-exceptions">Handling Exceptions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmunsecurevirtualmemory">MmUnsecureVirtualMemory</a>
 

 

