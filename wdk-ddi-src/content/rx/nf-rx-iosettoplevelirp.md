---
UID: NF:rx.IoSetTopLevelIrp
title: IoSetTopLevelIrp macro (rx.h)
description: The IoSetTopLevelIrp routine sets the value of the TopLevelIrp field of the current thread.
old-location: ifsk\iosettoplevelirp.htm
tech.root: ifsk
ms.assetid: 10d1889b-d79c-4c06-a012-77414c88ce17
ms.date: 04/16/2018
keywords: ["IoSetTopLevelIrp macro"]
ms.keywords: IoSetTopLevelIrp, IoSetTopLevelIrp routine [Installable File System Drivers], ifsk.iosettoplevelirp, ioref_1c046677-97df-4f46-956c-108a203f83f2.xml, ntifs/IoSetTopLevelIrp
req.header: rx.h
req.include-header: Rx.h, Wdm.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoSetTopLevelIrp
 - rx/IoSetTopLevelIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoSetTopLevelIrp
---

# IoSetTopLevelIrp macro


## -description

The <b>IoSetTopLevelIrp</b> routine sets the value of the <b>TopLevelIrp</b> field of the current thread.

## -parameters

### -param irp

<p>I/O request packet (IRP) pointer to be stored in the <b>TopLevelIrp</b> field of the current thread.</p>

## -remarks

<b>IoSetTopLevelIrp</b> sets the value of the <b>TopLevelIrp</b> field in the thread object for the current thread. This value can be <b>NULL</b>, a pointer to the current IRP, or an FSRTL flag. For more information about these values and what they mean, see the reference entry for <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp">IoGetTopLevelIrp</a>.

Only file systems can call <b>IoSetTopLevelIrp</b>. File system filters and minifilters cannot safely call this routine, because doing so can cause deadlocks.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp">IoGetTopLevelIrp</a>