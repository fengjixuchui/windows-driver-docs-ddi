---
UID: NF:miniport.InterlockedCompareExchange
title: InterlockedCompareExchange function (miniport.h)
description: The InterlockedCompareExchange routine performs an atomic operation that compares the input value pointed to by Destination with the value of Comparand.
old-location: kernel\interlockedcompareexchange.htm
tech.root: kernel
ms.assetid: 925a5481-d626-4824-8cbe-4fc2a0a6ad92
ms.date: 04/30/2018
keywords: ["InterlockedCompareExchange function"]
ms.keywords: InterlockedCompareExchange, InterlockedCompareExchange routine [Kernel-Mode Driver Architecture], k102_d40d8288-4c0d-43ed-af9f-3f9afabe1455.xml, kernel.interlockedcompareexchange, wdm/InterlockedCompareExchange
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
 - InterlockedCompareExchange
 - miniport/InterlockedCompareExchange
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
 - InterlockedCompareExchange
---

# InterlockedCompareExchange function (miniport.h)


## -description

The <b>InterlockedCompareExchange</b> routine performs an atomic operation that compares the input value pointed to by <i>Destination</i> with the value of <i>Comparand</i>.

## -parameters

### -param Destination 

[in, out]
A pointer to the input value that is compared with the value of <i>Comparand</i>.

### -param ExChange

<p>Specifies the output value pointed to by <i>Destination</i> if the input value pointed to by <i>Destination</i> equals the value of <i>Comparand</i>. </p>

### -param Comperand

<p>Specifies the value that is compared with the input value pointed to by <i>Destination</i>.</p>

## -returns

<b>InterlockedCompareExchange</b> returns the original value of *<i>Destination</i>.

## -remarks

If <i>Comparand</i> is equal to *<i>Destination</i>, then *<i>Destination</i> is set to equal <i>Exchange</i>. Otherwise, *<i>Destination</i> is unchanged.

<b>InterlockedCompareExchange</b> provides a fast, atomic way to synchronize the testing and updating of a variable that is shared by multiple threads. If the input value pointed to by <i>Destination</i> equals the value of <i>Comparand</i>, the output value of <i>Destination</i> is set to the value of <i>Exchange</i>. 

<b>InterlockedCompareExchange</b> is designed for speed and, typically, is implemented inline by a compiler. <b>InterlockedCompareExchange </b>is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. It does not use a spin lock and can be safely used on pageable data. 

Interlocked operations cannot be used on non-cached memory.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinterlockedcompareexchange64">ExInterlockedCompareExchange64</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedcompareexchangepointer">InterlockedCompareExchangePointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockeddecrement">InterlockedDecrement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedexchange">InterlockedExchange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedexchangepointer">InterlockedExchangePointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedincrement">InterlockedIncrement</a>

