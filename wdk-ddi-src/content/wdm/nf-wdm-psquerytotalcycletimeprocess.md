---
UID: NF:wdm.PsQueryTotalCycleTimeProcess
title: PsQueryTotalCycleTimeProcess function (wdm.h)
description: The PsQueryTotalCycleTimeProcess routine returns the accumulated cycle time for the specified process.
old-location: kernel\psquerytotalcycletimeprocess.htm
tech.root: kernel
ms.assetid: 4DA34F96-A69A-46BE-B3D8-D542794052DE
ms.date: 04/30/2018
keywords: ["PsQueryTotalCycleTimeProcess function"]
ms.keywords: PsQueryTotalCycleTimeProcess, PsQueryTotalCycleTimeProcess routine [Kernel-Mode Driver Architecture], kernel.psquerytotalcycletimeprocess, wdm/PsQueryTotalCycleTimeProcess
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PsQueryTotalCycleTimeProcess
 - wdm/PsQueryTotalCycleTimeProcess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - PsQueryTotalCycleTimeProcess
---

# PsQueryTotalCycleTimeProcess function


## -description

The <b>PsQueryTotalCycleTimeProcess</b> routine returns the accumulated cycle time for the specified process.

## -parameters

### -param Process 

[in, out]
A pointer to an <a href="/windows-hardware/drivers/kernel/eprocess">EPROCESS</a> structure that serves as the kernel object for the process.

### -param CycleTimeStamp 

[out]
A pointer to a ULONG64 variable to which the routine writes the current cycle counter value for the process.

## -returns

<b>PsQueryTotalCycleTimeProcess</b> returns the accumulated cycle time for the specified process.

## -remarks

This routine uses the time stamp counter to get the number of processor clock cycles used by the specified process.

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">EPROCESS</a>