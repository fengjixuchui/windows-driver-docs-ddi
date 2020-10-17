---
UID: NF:wdm.InterlockedExchangeAdd
title: InterlockedExchangeAdd function (wdm.h)
description: The InterlockedExchangeAdd routine adds a value to a given integer as an atomic operation and returns the original value of the given integer.
old-location: kernel\interlockedexchangeadd.htm
tech.root: kernel
ms.assetid: f61878b4-6bfa-463e-9fb1-c95171ce65b4
ms.date: 04/30/2018
keywords: ["InterlockedExchangeAdd function"]
ms.keywords: InterlockedExchangeAdd, InterlockedExchangeAdd routine [Kernel-Mode Driver Architecture], k102_ed690604-0379-476d-b838-4820f47b850a.xml, kernel.interlockedexchangeadd, wdm/InterlockedExchangeAdd
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.lib: OneCoreUAP.lib on Windows 10
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - InterlockedExchangeAdd
 - wdm/InterlockedExchangeAdd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - OneCoreUAP.lib
 - OneCoreUAP.dll
 - API-MS-Win-Core-Interlocked-l1-1-0.dll
 - API-MS-Win-Core-Interlocked-l1-2-0.dll
 - KernelBase.dll
 - MinKernelBase.dll
api_name:
 - InterlockedExchangeAdd
---

# InterlockedExchangeAdd function (wdm.h)


## -description

The <b>InterlockedExchangeAdd</b> routine adds a value to a given integer as an atomic operation and returns the original value of the given integer.

## -parameters

### -param Addend 

[in, out]
A pointer to an integer variable.

### -param Value 

[in]
Specifies the value to be added to <i>Addend</i>.

## -returns

<b>InterlockedExchangeAdd</b> returns the original value of the <i>Addend</i> variable when the call occurred.

## -remarks

<b>InterlockedExchangeAdd</b> should be used instead of <b>ExInterlockedAddUlong</b> because it is both faster and more efficient. 

<b>InterlockedExchangeAdd</b> is implemented inline by the compiler when appropriate and possible. It does not require a spin lock and can therefore be safely used on pageable data.

<b>InterlockedExchangeAdd</b> is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. 

Interlocked operations cannot be used on non-cached memory.

## -see-also

<a href="/previous-versions/ff545335(v=vs.85)">ExInterlockedAddLargeInteger</a>



<a href="/previous-versions/ff545343(v=vs.85)">ExInterlockedAddUlong</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockeddecrement">InterlockedDecrement</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedincrement">InterlockedIncrement</a>