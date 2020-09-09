---
UID: NF:ntifs.ZwFlushBuffersFileEx
title: ZwFlushBuffersFileEx function (ntifs.h)
description: The ZwFlushBuffersFileEx routine is called by a file system filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.
old-location: kernel\zwflushbuffersfileex.htm
tech.root: kernel
ms.assetid: C081CCF5-D13C-405C-A430-31805A16724A
ms.date: 04/30/2018
keywords: ["ZwFlushBuffersFileEx function"]
ms.keywords: FLUSH_FLAGS_FILE_DATA_ONLY, FLUSH_FLAGS_NO_SYNC, NtFlushBuffersFileEx, ZwFlushBuffersFileEx, ZwFlushBuffersFileEx routine [Kernel-Mode Driver Architecture], kernel.zwflushbuffersfileex, ntifs/NtFlushBuffersFileEx, ntifs/ZwFlushBuffersFileEx
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: PASSIVE_LEVEL (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwFlushBuffersFileEx
 - ntifs/ZwFlushBuffersFileEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwFlushBuffersFileEx
 - NtFlushBuffersFileEx
---

# ZwFlushBuffersFileEx function


## -description

The <b>ZwFlushBuffersFileEx</b> routine is called by a file system filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.

## -parameters

### -param FileHandle 

[in]
Handle returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile">ZwOpenFile</a> for the file whose buffers will be flushed. This parameter is required and cannot be <b>NULL</b>.

### -param FLags

<p>Flush operation flags. <i>Flags</i> can be 0 or one of the following values.</p>
  <table>
    <tr>
      <th>Value</th>
      <th>Meaning</th>
    </tr>
    <tr>
      <td width="40%">
        <a id="FLUSH_FLAGS_FILE_DATA_ONLY"></a>
        <a id="flush_flags_file_data_only"></a>
        <dl>
          <dt>
            <b>FLUSH_FLAGS_FILE_DATA_ONLY</b>
          </dt>
        </dl>
      </td>
      <td width="60%">
        <p>If the file is on an NTFS file system, file data in the file cache will be written. No metadata is written and the underlying storage is not synchronized to flush its cache. This flag is not valid with volume handles.</p>
      </td>
    </tr>
    <tr>
      <td width="40%">
        <a id="FLUSH_FLAGS_NO_SYNC"></a>
        <a id="flush_flags_no_sync"></a>
        <dl>
          <dt>
            <b>FLUSH_FLAGS_NO_SYNC</b>
          </dt>
        </dl>
      </td>
      <td width="60%">
        <p>If the file is on an NTFS file system, file data and metadata in the file cache will be written. The underlying storage is not synchronized to flush its cache. This flag is not valid with volume handles.</p>
      </td>
    </tr>
  </table>
  <p> </p>

### -param Parameters

<p>Address of the caller's I/O status block. This parameter is required and cannot be <b>NULL</b>.</p>

### -param ParametersSize

The size, in bytes, of the parameters block.

### -param IoStatusBlock 

[out]
Address of the caller's I/O status block. This parameter is required and cannot be <b>NULL</b>.

## -returns

<b>ZwFlushBuffersFileEx</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MEDIA_WRITE_PROTECTED</b></dt>
</dl>
</td>
<td width="60%">
The file resides on a write-protected volume; this is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>
</td>
<td width="60%">
The file resides on a volume that is not currently mounted; this is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The file does has neither write or append access.

</td>
</tr>
</table>

## -remarks

A file system filter driver can call <b>ZwFlushBuffersFileEx</b> to issue an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-flush-buffers">IRP_MJ_FLUSH_BUFFERS</a> request to the file system for a given file. The flush operation is synchronous. 

Minifilter drivers should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltflushbuffers">FltFlushBuffers</a> instead of calling <b>ZwFlushBuffersFileEx</b>. 

Callers of <b>ZwFlushBuffersFileEx</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwFlushBuffersFileEx</b> function occurs in user mode, you should use the name "<b>NtFlushBuffersFileEx</b>" instead of "<b>ZwFlushBuffersFileEx</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltflushbuffers">FltFlushBuffers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-flush-buffers">IRP_MJ_FLUSH_BUFFERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile">ZwOpenFile</a>

