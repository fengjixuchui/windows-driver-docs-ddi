---
UID: NF:wdm.IoGetStackLimits
title: IoGetStackLimits function (wdm.h)
description: The IoGetStackLimits routine returns the boundaries of the current thread's stack frame.
old-location: kernel\iogetstacklimits.htm
tech.root: kernel
ms.assetid: aaa10cb2-16cb-40a8-ad72-9715da311957
ms.date: 04/30/2018
keywords: ["IoGetStackLimits function"]
ms.keywords: IoGetStackLimits, IoGetStackLimits routine [Kernel-Mode Driver Architecture], k104_2688546a-d427-4d20-bc67-278b0fc20f45.xml, kernel.iogetstacklimits, wdm/IoGetStackLimits
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetStackLimits
 - wdm/IoGetStackLimits
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetStackLimits
---

# IoGetStackLimits function


## -description

The <b>IoGetStackLimits</b> routine returns the boundaries of the current thread's stack frame.

## -parameters

### -param LowLimit 

[out]
Pointer to a caller-supplied variable in which this routine returns the lower offset of the current thread's stack frame.

### -param HighLimit 

[out]
Pointer to a caller-supplied variable in which this routine returns the higher offset of the current thread's stack frame.

## -remarks

Highest-level drivers can call this routine, particularly file systems that have been passed a pointer to a location on the current thread's stack.

In Windows Server 2003 Service Pack 1 (SP1) and later versions of Windows, callers of <b>IoGetStackLimits</b> can be running at any IRQL. For earlier operating systems, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetinitialstack">IoGetInitialStack</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetremainingstacksize">IoGetRemainingStackSize</a>