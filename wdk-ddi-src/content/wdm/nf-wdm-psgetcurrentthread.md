---
UID: NF:wdm.PsGetCurrentThread
title: PsGetCurrentThread function (wdm.h)
description: The PsGetCurrentThread routine identifies the current thread.
old-location: kernel\psgetcurrentthread.htm
tech.root: kernel
ms.assetid: 132b30fe-21ef-48dc-8c69-02ccac563b87
ms.date: 04/30/2018
keywords: ["PsGetCurrentThread function"]
ms.keywords: ExGetCurrentResourceThread, PsGetCurrentThread, PsGetCurrentThread routine [Kernel-Mode Driver Architecture], k108_75fb6f47-8a13-4f2c-9b94-a8b7125bbcb6.xml, kernel.psgetcurrentthread, wdm/PsGetCurrentThread
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - PsGetCurrentThread
 - wdm/PsGetCurrentThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsGetCurrentThread
---

# PsGetCurrentThread function (wdm.h)


## -description

The <b>PsGetCurrentThread</b> routine identifies the current thread.

## -returns

<b>PsGetCurrentThread</b> returns a pointer to the executive thread object that represents the currently executing thread.

## -remarks

This macro

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentthread">KeGetCurrentThread</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pscreatesystemthread">PsCreateSystemThread</a>



[PsGetCurrentProcess](/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentprocessid">PsGetCurrentProcessId</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psissystemthread">PsIsSystemThread</a>