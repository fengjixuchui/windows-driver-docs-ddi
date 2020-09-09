---
UID: NF:miniport.InterlockedExchange
title: InterlockedExchange function (miniport.h)
description: The InterlockedExchange routine sets an integer variable to a given value as an atomic operation.
old-location: kernel\interlockedexchange.htm
tech.root: kernel
ms.assetid: c9bee5b0-eeaf-4c82-9f02-d00cf9202f78
ms.date: 04/30/2018
keywords: ["InterlockedExchange function"]
ms.keywords: InterlockedExchange, InterlockedExchange routine [Kernel-Mode Driver Architecture], k102_ae8d85b7-040e-4c44-9476-68d6919a50e4.xml, kernel.interlockedexchange, wdm/InterlockedExchange
req.header: miniport.h
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
 - InterlockedExchange
 - miniport/InterlockedExchange
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
 - InterlockedExchange
---

# InterlockedExchange function (miniport.h)


## -description

The <b>InterlockedExchange</b> routine sets an integer variable to a given value as an atomic operation.

## -parameters

### -param Target 

[in, out]
A pointer to a variable to be set to the supplied <i>Value</i> as an atomic operation.

### -param Value 

[in]
Specifies the value to which the variable will be set.

## -returns

<b>InterlockedExchange</b> returns the value of the variable at <i>Target</i> when the call occurred.

## -remarks

<b>InterlockedExchange</b> should be used instead of <b>ExInterlockedExchangeUlong</b>, because it is both faster and more efficient. 

<b>InterlockedExchange</b> is implemented inline by the compiler when appropriate and possible. It does not require a spin lock and can therefore be safely used on pageable data.

A call to <b>InterlockedExchange</b> routine is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. 

Interlocked operations cannot be used on non-cached memory.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545335">ExInterlockedAddLargeInteger</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545343">ExInterlockedAddUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockeddecrement">InterlockedDecrement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedincrement">InterlockedIncrement</a>

