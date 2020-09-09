---
UID: NF:wdm.KeQueryAuxiliaryCounterFrequency
title: KeQueryAuxiliaryCounterFrequency function (wdm.h)
description: The KeQueryAuxiliaryCounterFrequency routine returns frequency of the auxiliary counter in units of Hz.
old-location: kernel\kequeryauxiliarycounterfrequency.htm
tech.root: kernel
ms.assetid: E7F9549D-F222-42BF-B82B-B0DA0F6BC60F
ms.date: 04/30/2018
keywords: ["KeQueryAuxiliaryCounterFrequency function"]
ms.keywords: KeQueryAuxiliaryCounterFrequency, KeQueryAuxiliaryCounterFrequency routine [Kernel-Mode Driver Architecture], kernel.kequeryauxiliarycounterfrequency, wdm/KeQueryAuxiliaryCounterFrequency
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.lib: Ntoskrnl.lib
req.dll: Hal.dll
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KeQueryAuxiliaryCounterFrequency
 - wdm/KeQueryAuxiliaryCounterFrequency
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hal.dll
api_name:
 - KeQueryAuxiliaryCounterFrequency
---

# KeQueryAuxiliaryCounterFrequency function


## -description

The <b>KeQueryAuxiliaryCounterFrequency</b> routine returns frequency of the auxiliary counter in units of Hz.

## -parameters

### -param AuxiliaryCounterFrequency 

[out, optional]
A pointer to a variable to which <b>KeQueryAuxiliaryCounterFrequency</b> writes the auxiliary counter frequency, in ticks per second. This parameter can be NULL.

## -returns

<b>KeQueryAuxiliaryCounterFrequency</b> can return one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The query succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Auxiliary counter is not supported.

</td>
</tr>
</table>

## -remarks

Call this routine to programmatically determine whether auxiliary counter is supported. In that call, if you do not need the frequency of the counter, pass NULL. If not supported, the routine returns STATUS_NOT_SUPPORTED.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keconvertauxiliarycountertoperformancecounter">KeConvertAuxiliaryCounterToPerformanceCounter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keconvertperformancecountertoauxiliarycounter">KeConvertPerformanceCounterToAuxiliaryCounter</a>

