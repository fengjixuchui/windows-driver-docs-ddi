---
UID: NF:wdm.MmUnlockPages
title: MmUnlockPages function (wdm.h)
description: The MmUnlockPages routine unlocks the physical pages that are described by the specified memory descriptor list (MDL).
old-location: kernel\mmunlockpages.htm
tech.root: kernel
ms.assetid: 506f5fef-11fa-4d65-a180-c613cd8a8e1e
ms.date: 04/30/2018
ms.keywords: MmUnlockPages, MmUnlockPages routine [Kernel-Mode Driver Architecture], k106_b8d8a984-9e0e-4322-bce1-2dd79e8d3a10.xml, kernel.mmunlockpages, wdm/MmUnlockPages
ms.topic: function
f1_keywords:
 - "wdm/MmUnlockPages"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmUnlockPages
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmUnlockPages function


## -description


The <b>MmUnlockPages</b> routine unlocks the physical pages that are described by the specified memory descriptor list (MDL).


## -parameters




### -param MemoryDescriptorList [in, out]

A pointer to an MDL.


## -returns



None




## -remarks



The memory described by the specified MDL must have been locked previously by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>. If the specified MDL is mapped to system address space, <b>MmUnlockPages</b> releases this mapping before it unlocks the pages.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>
 

 

