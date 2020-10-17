---
UID: NF:wdm.ClfsReadNextLogRecord
title: ClfsReadNextLogRecord function (wdm.h)
description: The ClfsReadNextLogRecord routine reads the next record in a sequence, relative to the current record in a read context.
old-location: kernel\clfsreadnextlogrecord.htm
tech.root: kernel
ms.assetid: 4990f3d7-e48c-49ee-9384-4bcad93c9281
ms.date: 04/30/2018
keywords: ["ClfsReadNextLogRecord function"]
ms.keywords: ClfsReadNextLogRecord, ClfsReadNextLogRecord routine [Kernel-Mode Driver Architecture], Clfs_4e00ce69-12c3-48c1-ba3b-1c85158afc12.xml, kernel.clfsreadnextlogrecord, wdm/ClfsReadNextLogRecord
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
 - ClfsReadNextLogRecord
 - wdm/ClfsReadNextLogRecord
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsReadNextLogRecord
---

# ClfsReadNextLogRecord function


## -description

The <b>ClfsReadNextLogRecord</b> routine reads the next record in a sequence, relative to the current record in a read context.

## -parameters

### -param pvReadContext 

[in, out]
A pointer to a read context that the caller previously obtained by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadlogrecord">ClfsReadLogRecord</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadrestartarea">ClfsReadRestartArea</a>.

### -param ppvBuffer 

[out]
A pointer to a variable that receives a pointer to a buffer that contains the record data.

### -param pcbBuffer 

[out]
A pointer to a ULONG-typed variable that receives the size, in bytes, of the buffer pointed to by *<i>ppvBuffer</i>. This is the length of the data buffer of the record read.

### -param peRecordType 

[in, out]
A pointer to a variable of type CLFS_RECORD_TYPE. The caller must set this parameter to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Record that will be read</th>
</tr>
<tr>
<td>
<b>ClfsDataRecord</b>

</td>
<td>
The next data record.

</td>
</tr>
<tr>
<td>
<b>ClfsRestartRecord</b>

</td>
<td>
The next restart record.

</td>
</tr>
<tr>
<td>
<b>ClfsClientRecord</b>

</td>
<td>
The next record that is either a data record or a restart record.

</td>
</tr>
</table>

### -param plsnUser 

[in, optional]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that supplies the LSN of the record to be read. The specified record is read instead of the record that would have been read according to the mode (<b>ClfsContextUndoNext</b>, <b>ClfsContextPrevious</b>, or <b>ClfsContextForward</b>) of the read context (<i>pvReadContext</i>). The LSN supplied in <i>plsnUser</i> must be less than the current LSN of the read context. This parameter can be <b>NULL</b>.

### -param plsnUndoNext 

[out]
A pointer to a <b>CLFS_LSN</b> structure that receives the undo-next LSN of the record that is read.

### -param plsnPrevious 

[out]
A pointer to a <b>CLFS_LSN</b> structure that receives the previous LSN of the record that was read.

### -param plsnRecord 

[out]
A pointer to a <b>CLFS_LSN</b> structure that receives the LSN of the record that was read.

## -returns

<b>ClfsReadNextLogRecord</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

For an explanation of CLFS concepts and terminology, see <a href="/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 

For information about reading records from CLFS streams, see <a href="/windows-hardware/drivers/kernel/reading-data-records-from-a-clfs-stream">Reading Data Records from a CLFS Stream</a> and <a href="/windows-hardware/drivers/kernel/reading-restart-records-from-a-clfs-stream">Reading Restart Records from a CLFS Stream</a>.

Read contexts are not thread-safe. Clients are responsible for serializing access to read contexts.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadlogrecord">ClfsReadLogRecord</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadrestartarea">ClfsReadRestartArea</a>