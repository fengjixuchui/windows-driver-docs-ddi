---
UID: NF:wdm.ExAllocateFromPagedLookasideList
title: ExAllocateFromPagedLookasideList function (wdm.h)
description: The ExAllocateFromPagedLookasideList routine returns a pointer to a paged entry from the given lookaside list, or it returns a pointer to a newly allocated paged entry.
old-location: kernel\exallocatefrompagedlookasidelist.htm
tech.root: kernel
ms.assetid: f0c86720-4914-47b1-abb1-151196cc2a68
ms.date: 04/30/2018
keywords: ["ExAllocateFromPagedLookasideList function"]
ms.keywords: ExAllocateFromPagedLookasideList, ExAllocateFromPagedLookasideList routine [Kernel-Mode Driver Architecture], k102_96e03fc6-f951-4c96-8de4-32d67e85ec02.xml, kernel.exallocatefrompagedlookasidelist, wdm/ExAllocateFromPagedLookasideList
f1_keywords:
 - "wdm/ExAllocateFromPagedLookasideList"
 - "ExAllocateFromPagedLookasideList"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExAllocateFromPagedLookasideList
targetos: Windows
req.typenames: 
---

# ExAllocateFromPagedLookasideList function


## -description


The <b>ExAllocateFromPagedLookasideList</b> routine returns a pointer to a paged entry from the given lookaside list, or it returns a pointer to a newly allocated paged entry. 


## -parameters




### -param Lookaside [in, out]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">PAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller already initialized with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializepagedlookasidelist">ExInitializePagedLookasideList</a>. 


## -returns



<b>ExAllocateFromPagedLookasideList</b> returns a pointer to an entry if one can be allocated. Otherwise, it returns <b>NULL</b>.




## -remarks



If the given lookaside list is not empty, <b>ExAllocateFromPagedLookasideList</b> removes the first entry from the list and returns a pointer to this entry. Otherwise, <b>ExAllocateFromPagedLookasideList</b> either calls the <i>Allocate</i> routine specified at list initialization or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a> to return an entry pointer.

The caller can then set up the returned entry with any caller-determined data. The caller should release each entry with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetopagedlookasidelist">ExFreeToPagedLookasideList</a> when it is no longer in use. 

Because the entries in a paged lookaside list are allocated from pageable memory, they must not be accessed at an IRQL >= DISPATCH_LEVEL. You can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a> to create a lookaside list with non-pageable entries.

On Windows 2000, drivers must use the <b>-D_WIN2K_COMPAT_SLIST_USAGE</b> switch to successfully link code that uses <b>ExAllocateFromPagedLookasideList</b>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-lookaside-lists">Using Lookaside Lists</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetopagedlookasidelist">ExFreeToPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializepagedlookasidelist">ExInitializePagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">PAGED_LOOKASIDE_LIST</a>
 

 

