---
UID: NF:ntddk.IoVolumeDeviceToDosName
title: IoVolumeDeviceToDosName function (ntddk.h)
description: The IoVolumeDeviceToDosName routine returns the MS-DOS path for a specified device object that represents a file system volume.
old-location: kernel\iovolumedevicetodosname.htm
tech.root: kernel
ms.assetid: f860d0ad-f971-4ba7-93fb-20fe8831fc90
ms.date: 04/30/2018
keywords: ["IoVolumeDeviceToDosName function"]
ms.keywords: IoVolumeDeviceToDosName, IoVolumeDeviceToDosName routine [Kernel-Mode Driver Architecture], k104_01cdeb80-9a49-4d42-a311-cf8b69d03b9c.xml, kernel.iovolumedevicetodosname, ntddk/IoVolumeDeviceToDosName
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP. Drivers that must work in earlier versions of Windows NT-based operating systems can use RtlVolumeDeviceToDosName, which behaves identically.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoVolumeDeviceToDosName
 - ntddk/IoVolumeDeviceToDosName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoVolumeDeviceToDosName
---

# IoVolumeDeviceToDosName function


## -description

The <b>IoVolumeDeviceToDosName</b> routine returns the MS-DOS path for a specified device object that represents a file system volume.

## -parameters

### -param VolumeDeviceObject 

[in]
A pointer to a device object that represents a volume device object created by a storage class driver.

### -param DosName 

[out]
A pointer to a caller-allocated <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure. If the call is successful, <b>IoVolumeDeviceToDosName</b> sets the values of the <b>Length</b>, <b>MaximumLength</b>, and <b>Buffer</b> members of this structure. On exit, the <b>Buffer</b> member points to a wide-character, null-terminated string that contains the MS-DOS path of the volume device object specified by <i>VolumeDeviceObject</i>. For more information, see Remarks.

## -returns

<b>IoVolumeDeviceToDosName</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>
</td>
<td width="60%">
The routine failed due to invalid parameter values passed by the caller.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl>
</td>
<td width="60%">
The routine failed to allocate resources required for this operation.

</td>
</tr>
</table>

## -remarks

<b>IoVolumeDeviceToDosName</b> allocates the string buffer pointed to by the <b>Buffer</b> member of the <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that the <i>DosName</i> parameter points to. After this buffer is no longer required, a caller of this routine should call the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a> routine to free the buffer.

Starting with Windows Vista, you must ensure that APCs are <u>not</u> disabled before calling this routine. The <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keareallapcsdisabled">KeAreAllApcsDisabled</a> routine can be used to verify that APCs are not disabled.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keareallapcsdisabled">KeAreAllApcsDisabled</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>