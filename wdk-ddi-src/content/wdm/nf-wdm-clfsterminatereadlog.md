---
UID: NF:wdm.ClfsTerminateReadLog
title: ClfsTerminateReadLog function (wdm.h)
description: The ClfsTerminateReadLog routine invalidates a specified read context after freeing resources associated with the context.
old-location: kernel\clfsterminatereadlog.htm
tech.root: kernel
ms.assetid: 47633903-0314-4d50-8dd5-ddb0eb934e09
ms.date: 04/30/2018
keywords: ["ClfsTerminateReadLog function"]
ms.keywords: ClfsTerminateReadLog, ClfsTerminateReadLog routine [Kernel-Mode Driver Architecture], Clfs_691e308a-56d7-498f-af11-8908cc13b1b7.xml, kernel.clfsterminatereadlog, wdm/ClfsTerminateReadLog
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsTerminateReadLog
 - wdm/ClfsTerminateReadLog
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsTerminateReadLog
---

# ClfsTerminateReadLog function


## -description

The <b>ClfsTerminateReadLog</b> routine invalidates a specified read context after freeing resources associated with the context.

## -parameters

### -param pvCursorContext 

[in]
A pointer to the read context to be invalidated. The caller previously obtained this pointer by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadlogrecord">ClfsReadLogRecord</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadrestartarea">ClfsReadRestartArea</a>.

## -returns

<b>ClfsTerminateReadLog</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

<div class="alert"><b>Warning</b>    Failure to call this routine can lead to memory leaks, premature exhaustion of log I/O blocks, and increased frequency of log flushes.<p class="note">Attempting to use <i>pvCursorContext</i> after it is freed is equivalent to accessing freed memory and can lead to unexpected behavior.

</div>
<div> </div>
For an explanation of CLFS concepts and terminology, see <a href="/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadlogrecord">ClfsReadLogRecord</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadrestartarea">ClfsReadRestartArea</a>