---
UID: NF:ntddk.RtlRunOnceInitialize
title: RtlRunOnceInitialize function (ntddk.h)
description: The RtlRunOnceInitialize routine initializes a RTL_RUN_ONCE structure.
old-location: kernel\rtlrunonceinitialize.htm
tech.root: kernel
ms.assetid: 4d1a65af-a475-4360-9db3-d5b9e302697d
ms.date: 04/30/2018
keywords: ["RtlRunOnceInitialize function"]
ms.keywords: RtlRunOnceInitialize, RtlRunOnceInitialize routine [Kernel-Mode Driver Architecture], k109_7d98d21e-b6f2-4ccd-b447-0c1d612eed5b.xml, kernel.rtlrunonceinitialize, ntddk/RtlRunOnceInitialize
f1_keywords:
 - "ntddk/RtlRunOnceInitialize"
 - "RtlRunOnceInitialize"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
- RtlRunOnceInitialize
targetos: Windows
req.typenames: 
---

# RtlRunOnceInitialize function


## -description


The <b>RtlRunOnceInitialize</b> routine initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_RUN_ONCE</a> structure.


## -parameters




### -param RunOnce [out]

Pointer to the <b>RTL_RUN_ONCE</b> one-time initialization structure.


## -returns



None 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_RUN_ONCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrunoncebegininitialize">RtlRunOnceBeginInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrunoncecomplete">RtlRunOnceComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlrunonceexecuteonce">RtlRunOnceExecuteOnce</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-rtl_run_once_init_fn">RunOnceInitialization</a>
 

 

