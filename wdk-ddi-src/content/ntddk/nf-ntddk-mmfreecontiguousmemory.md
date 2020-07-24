---
UID: NF:ntddk.MmFreeContiguousMemory
title: MmFreeContiguousMemory function (ntddk.h)
description: The MmFreeContiguousMemory routine releases a range of physically contiguous memory that was allocated by an MmAllocateContiguousMemoryXxx routine.
old-location: kernel\mmfreecontiguousmemory.htm
tech.root: kernel
ms.assetid: 485c9b03-eb45-4c86-9292-ccd51ba7b080
ms.date: 04/30/2018
keywords: ["MmFreeContiguousMemory function"]
ms.keywords: MmFreeContiguousMemory, MmFreeContiguousMemory routine [Kernel-Mode Driver Architecture], k106_1b930a75-7382-4a6c-a638-3e7675f43f83.xml, kernel.mmfreecontiguousmemory, wdm/MmFreeContiguousMemory
f1_keywords:
 - "ntddk/MmFreeContiguousMemory"
 - "MmFreeContiguousMemory"
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmDispatch, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmFreeContiguousMemory
targetos: Windows
req.typenames: 
---

# MmFreeContiguousMemory function


## -description


The <b>MmFreeContiguousMemory</b> routine releases a range of physically contiguous memory that was allocated by an <b>MmAllocateContiguousMemory<i>Xxx</i></b> routine.


## -parameters




### -param BaseAddress [in]

Pointer to the virtual address of the memory to be freed.


## -remarks



The <b>MmFreeContiguousMemory</b> routine frees a block of physically contiguous memory that was allocated by a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemory">MmAllocateContiguousMemory</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycache">MmAllocateContiguousMemorySpecifyCache</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycachenode">MmAllocateContiguousMemorySpecifyCacheNode</a> routine. The <i>BaseAddress</i> parameter must be the base address that was obtained from the previous call to the <b>MmAllocateContiguousMemory<i>Xxx</i></b> routine.

A device driver that must use contiguous memory should allocate only what it needs during driver initialization because physical memory is likely to become fragmented as the system runs. Such a driver must deallocate the memory when the driver is done using the memory.

Callers of <b>MmFreeContiguousMemory</b> must be running at IRQL = APC_LEVEL. For Windows Server 2008 and later versions of the Windows operating system, you can also call <b>MmFreeContiguousMemory</b> with IRQL <= DISPATCH_LEVEL. However, you can improve driver performance by calling at APC_LEVEL or below.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemory">MmAllocateContiguousMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycache">MmAllocateContiguousMemorySpecifyCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycachenode">MmAllocateContiguousMemorySpecifyCacheNode</a>
 

 

