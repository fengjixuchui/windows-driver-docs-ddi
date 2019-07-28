---
UID: NF:wdm.ClfsReadPreviousRestartArea
title: ClfsReadPreviousRestartArea function (wdm.h)
description: The ClfsReadPreviousRestartArea routine reads the previous restart record relative to the current record in a read context.
old-location: kernel\clfsreadpreviousrestartarea.htm
tech.root: kernel
ms.assetid: 832da270-e1e1-41bf-a9cf-0b363c0d2d74
ms.date: 04/30/2018
ms.keywords: ClfsReadPreviousRestartArea, ClfsReadPreviousRestartArea routine [Kernel-Mode Driver Architecture], Clfs_884a8a2f-adbf-415b-968e-2f82c3f5d7fa.xml, kernel.clfsreadpreviousrestartarea, wdm/ClfsReadPreviousRestartArea
ms.topic: function
f1_keywords:
 - "wdm/ClfsReadPreviousRestartArea"
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsReadPreviousRestartArea
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsReadPreviousRestartArea function


## -description


The <b>ClfsReadPreviousRestartArea</b> routine reads the previous restart record relative to the current record in a read context.


## -parameters




### -param pvReadContext [in]

A pointer to a read context obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfsreadrestartarea">ClfsReadRestartArea</a>.


### -param ppvRestartBuffer [out]

A pointer to a variable that receives a pointer to the data buffer of the restart record that is read.


### -param pcbRestartBuffer [out]

A pointer to a ULONG-typed variable that receives the size, in bytes, of the buffer pointed to by *<i>ppvRestartBuffer</i>. This is the length of the data buffer of the restart record that is read.


### -param plsnRestart [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that receives the previous LSN of the restart record that was read.


## -returns



<b>ClfsReadPreviousRestartArea</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h. If there are no previous restart areas, the return value is STATUS_LOG_START_OF_LOG.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

For information about reading records from CLFS streams, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/reading-data-records-from-a-clfs-stream">Reading Data Records from a CLFS Stream</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/reading-restart-records-from-a-clfs-stream">Reading Restart Records from a CLFS Stream</a>.

Read contexts are not thread-safe. Clients are responsible for serializing access to read contexts.

Clients append restart records to a CLFS log by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfswriterestartarea">ClfsWriteRestartArea</a>.       

With the <b>ReadPreviousLogRestartArea</b> routine, clients can implement a form of fuzzy checkpointing. For example, the checkpoint state could consist of the log records delimited by two or more restart records. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfsreadrestartarea">ClfsReadRestartArea</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfswriterestartarea">ClfsWriteRestartArea</a>
 

 

