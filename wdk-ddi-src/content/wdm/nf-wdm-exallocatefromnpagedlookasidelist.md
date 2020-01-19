---
UID: NF:wdm.ExAllocateFromNPagedLookasideList
title: ExAllocateFromNPagedLookasideList function (wdm.h)
description: The ExAllocateFromNPagedLookasideList routine returns a pointer to a nonpaged entry from the given lookaside list, or it returns a pointer to a newly allocated nonpaged entry.
old-location: kernel\exallocatefromnpagedlookasidelist.htm
tech.root: kernel
ms.assetid: f62c63f0-cf17-4308-97f1-84bb668d2d51
ms.date: 04/30/2018
ms.keywords: ExAllocateFromNPagedLookasideList, ExAllocateFromNPagedLookasideList routine [Kernel-Mode Driver Architecture], k102_43919c0e-8140-4fc8-80f5-1955e39aa493.xml, kernel.exallocatefromnpagedlookasidelist, wdm/ExAllocateFromNPagedLookasideList
ms.topic: function
f1_keywords:
 - "wdm/ExAllocateFromNPagedLookasideList"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExAllocateFromNPagedLookasideList
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExAllocateFromNPagedLookasideList function


## -description


The <b>ExAllocateFromNPagedLookasideList</b> routine returns a pointer to a nonpaged entry from the given lookaside list, or it returns a pointer to a newly allocated nonpaged entry. 


## -parameters




### -param Lookaside [in, out]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">NPAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller already initialized with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializenpagedlookasidelist">ExInitializeNPagedLookasideList</a>. 


## -returns



<b>ExAllocateFromNPagedLookasideList</b> returns a pointer to an entry if one can be allocated. Otherwise, it returns <b>NULL</b>.




## -remarks



If the given lookaside list is not empty, <b>ExAllocateFromNPagedLookasideList</b> removes the first entry from the list and returns a pointer to this entry. Otherwise, <b>ExAllocateFromNPagedLookasideList</b> either calls the <i>Allocate</i> routine specified at list initialization or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a> to return an entry pointer.

The caller can then set up the returned entry with any caller-determined data. For example, a driver might use each such fixed-size entry to set up command blocks, like SCSI SRBs, to peripheral devices on a particular type of I/O bus. The caller should release each entry with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetonpagedlookasidelist">ExFreeToNPagedLookasideList</a> when it is no longer in use.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-lookaside-lists">Using Lookaside Lists</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefrompagedlookasidelist">ExAllocateFromPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetonpagedlookasidelist">ExFreeToNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializenpagedlookasidelist">ExInitializeNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">NPAGED_LOOKASIDE_LIST</a>
 

 

