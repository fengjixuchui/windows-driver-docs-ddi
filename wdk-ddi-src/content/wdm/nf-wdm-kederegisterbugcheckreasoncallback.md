---
UID: NF:wdm.KeDeregisterBugCheckReasonCallback
title: KeDeregisterBugCheckReasonCallback function (wdm.h)
description: The KeDeregisterBugCheckReasonCallback routine removes a callback routine that was registered by KeRegisterBugCheckReasonCallback.
old-location: kernel\kederegisterbugcheckreasoncallback.htm
tech.root: kernel
ms.assetid: 3a2a8940-afe2-48f5-bcf0-abd6413eeb85
ms.date: 04/30/2018
keywords: ["KeDeregisterBugCheckReasonCallback function"]
ms.keywords: KeDeregisterBugCheckReasonCallback, KeDeregisterBugCheckReasonCallback routine [Kernel-Mode Driver Architecture], k105_f767309b-2c8a-4460-a43f-06aec0f7d401.xml, kernel.kederegisterbugcheckreasoncallback, wdm/KeDeregisterBugCheckReasonCallback
f1_keywords:
 - "wdm/KeDeregisterBugCheckReasonCallback"
 - "KeDeregisterBugCheckReasonCallback"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP Service Pack 1 (SP1), Windows Server 2003, and later versions of Windows.
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeDeregisterBugCheckReasonCallback
targetos: Windows
req.typenames: 
---

# KeDeregisterBugCheckReasonCallback function


## -description


The <b>KeDeregisterBugCheckReasonCallback</b> routine removes a callback routine that was registered by <b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback">KeRegisterBugCheckReasonCallback</a></b>.


## -parameters




### -param CallbackRecord [in, out]

Pointer to a <b><a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KBUGCHECK_REASON_CALLBACK_RECORD</a></b> structure. <i>CallbackRecord</i> must be the same value that was passed to <b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback">KeRegisterBugCheckReasonCallback</a></b> when the callback was registered.


## -returns



<b>KeDeregisterBugCheckReasonCallback</b> returns <b>TRUE</b> if the callback is successfully removed. It returns <b>FALSE</b> if the specified callback is not registered.




## -see-also




<b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback">KeRegisterBugCheckReasonCallback</a></b>
 

 

