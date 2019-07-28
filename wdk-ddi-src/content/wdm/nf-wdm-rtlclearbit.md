---
UID: NF:wdm.RtlClearBit
title: RtlClearBit function (wdm.h)
description: The RtlClearBit routine sets the specified bit in a bitmap to zero.
old-location: kernel\rtlclearbit.htm
tech.root: kernel
ms.assetid: bfc75a17-a0de-436e-aebf-902fd841871a
ms.date: 04/30/2018
ms.keywords: RtlClearBit, RtlClearBit routine [Kernel-Mode Driver Architecture], k109_f785121e-f076-4f31-90ab-4bec446e3cc9.xml, kernel.rtlclearbit, wdm/RtlClearBit
ms.topic: function
f1_keywords:
 - "wdm/RtlClearBit"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: "<= APC_LEVEL (See Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlClearBit
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlClearBit function


## -description


The <b>RtlClearBit</b> routine sets the specified bit in a bitmap to zero. 


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a> routine. 


### -param BitNumber [in]

Specifies the zero-based index of the bit within the bitmap. The routine sets this bit to zero. 


## -returns



None




## -remarks



Callers of <b>RtlClearBit</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlClearBit</b> can be called at any IRQL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a>
 

 

