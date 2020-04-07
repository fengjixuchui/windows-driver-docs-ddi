---
UID: NF:wdm.ZwMapViewOfSection
title: ZwMapViewOfSection function (wdm.h)
description: The ZwMapViewOfSection routine maps a view of a section into the virtual address space of a subject process.
old-location: kernel\zwmapviewofsection.htm
tech.root: kernel
ms.assetid: 2abe7751-ef8c-4511-aaf6-755428c451fe
ms.date: 04/30/2018
keywords: ["ZwMapViewOfSection function"]
ms.keywords: NtMapViewOfSection, ZwMapViewOfSection, ZwMapViewOfSection routine [Kernel-Mode Driver Architecture], k111_cdad5afa-13b3-415e-96e8-688e7984a9fd.xml, kernel.zwmapviewofsection, wdm/NtMapViewOfSection, wdm/ZwMapViewOfSection
f1_keywords:
 - "wdm/ZwMapViewOfSection"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
- ZwMapViewOfSection
- NtMapViewOfSection
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwMapViewOfSection function


## -description


The <b>ZwMapViewOfSection</b> routine maps a view of a section into the virtual address space of a subject process.


## -parameters




### -param SectionHandle [in]

Handle to a section object. This handle is created by a successful call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatesection">ZwCreateSection</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopensection">ZwOpenSection</a>.


### -param ProcessHandle [in]

Handle to the object that represents the process that the view should be mapped into. Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">ZwCurrentProcess</a> macro to specify the current process. The handle must have been opened with PROCESS_VM_OPERATION access (described in the Microsoft Windows SDK documentation).


### -param BaseAddress [in, out]

Pointer to a variable that receives the base address of the view. If the value of this parameter is not <b>NULL</b>, the view is allocated starting at the specified virtual address rounded down to the next 64-kilobyte address boundary.


### -param ZeroBits [in]

Specifies the number of high-order address bits that must be zero in the base address of the section view. The value of this parameter must be less than 21 and is used only if <i>BaseAddress</i> is <b>NULL</b>—in other words, when the caller allows the system to determine where to allocate the view.


### -param CommitSize [in]

Specifies the size, in bytes, of the initially committed region of the view. <i>CommitSize</i> is meaningful only for page-file backed sections and is rounded up to the nearest multiple of PAGE_SIZE. (For sections that map files, both the data and the image are committed at section-creation time.)


### -param SectionOffset [in, out, optional]

A pointer to a variable that receives the offset, in bytes, from the beginning of the section to the view. If this pointer is not <b>NULL</b>, the offset is rounded down to the next allocation-granularity size boundary.


### -param ViewSize [in, out]

A pointer to a SIZE_T variable. If the initial value of this variable is zero, <b>ZwMapViewOfSection</b> maps a view of the section that starts at <i>SectionOffset</i> and continues to the end of the section. Otherwise, the initial value specifies the view's size, in bytes. <b>ZwMapViewOfSection</b> always rounds this value up to the nearest multiple of PAGE_SIZE before mapping the view.

On return, the value receives the actual size, in bytes, of the view.


### -param InheritDisposition [in]

Specifies how the view is to be shared with child processes. The possible values are:





#### ViewShare

The view will be mapped into any child processes that are created in the future.



#### ViewUnmap

The view will not be mapped into child processes.

Drivers should typically specify <b>ViewUnmap</b> for this parameter.


### -param AllocationType [in]

Specifies a set of flags that describes the type of allocation to be performed for the specified region of pages. The valid flags are MEM_LARGE_PAGES, MEM_RESERVE, and MEM_TOP_DOWN. Although MEM_COMMIT is not allowed, it is implied unless MEM_RESERVE is specified. For more information about the MEM_<i>XXX</i> flags, see the description of the <a href="https://docs.microsoft.com/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc">VirtualAlloc</a> routine.


### -param Win32Protect [in]

Specifies the type of protection for the region of initially committed pages. Device and intermediate drivers should set this value to PAGE_READWRITE.


## -returns



<b>ZwMapViewOfSection</b> returns an NTSTATUS value. Possible return values include the following:

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
The routine successfully performed the requested operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONFLICTING_ADDRESSES</b></dt>
</dl>
</td>
<td width="60%">
The specified address range conflicts with an address range already reserved, or the specified cache attribute type conflicts with the address range's existing cache attribute. For example, if the memory being mapped lies within a large page that is already mapped as fully cached, then it is illegal to request to map this memory as noncached or write combined.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PAGE_PROTECTION</b></dt>
</dl>
</td>
<td width="60%">
The value specified for the <i>Protect</i> parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SECTION_PROTECTION </b></dt>
</dl>
</td>
<td width="60%">
The value specified for the <i>AllocationType</i> parameter is incompatible with the protection type specified when the section was created.

</td>
</tr>
</table>
 




## -remarks



Several different views of a section can be concurrently mapped into the virtual address space of one or more processes.

If the specified section does not exist or the access requested is not allowed, <b>ZwMapViewOfSection</b> returns an error.

Do not use <b>ZwMapViewOfSection</b> to map a memory range from <b>\Device\PhysicalMemory</b> into user mode—unless your driver has directly allocated the memory range through <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdl">MmAllocatePagesForMdl</a> or another method guaranteeing that no other system component has mapped the same memory range with a different <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a> value.

User applications cannot access <b>\Device\PhysicalMemory</b> directly starting with Windows Server 2003 with Service Pack 1 (SP1) and can access it only if the driver passes a handle to the application.

For more information about section objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/section-objects-and-views">Section Objects and Views</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtMapViewOfSection</b>" instead of "<b>ZwMapViewOfSection</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdl">MmAllocatePagesForMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc">VirtualAlloc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">ZwCurrentProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopensection">ZwOpenSection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwunmapviewofsection">ZwUnmapViewOfSection</a>
 

 

