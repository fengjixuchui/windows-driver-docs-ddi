---
UID: NF:fltkernel.FltIsVolumeWritable
title: FltIsVolumeWritable function (fltkernel.h)
description: The FltIsVolumeWritable routine determines whether the disk device that corresponds to a volume or minifilter driver instance is writable.
old-location: ifsk\fltisvolumewritable.htm
tech.root: ifsk
ms.assetid: 9347bc8d-e8fb-440c-8ceb-ce5e8cb1429e
ms.date: 04/16/2018
keywords: ["FltIsVolumeWritable function"]
ms.keywords: FltApiRef_e_to_o_8b8316b0-5943-425e-a978-a2999629f93c.xml, FltIsVolumeWritable, FltIsVolumeWritable routine [Installable File System Drivers], fltkernel/FltIsVolumeWritable, ifsk.fltisvolumewritable
f1_keywords:
 - "fltkernel/FltIsVolumeWritable"
 - "FltIsVolumeWritable"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltIsVolumeWritable routine is available in Windows Vista and later versions of Windows.
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltIsVolumeWritable
targetos: Windows
req.typenames: 
---

# FltIsVolumeWritable function


## -description


The <b>FltIsVolumeWritable</b> routine determines whether the disk device that corresponds to a volume or minifilter driver instance is writable.


## -parameters




### -param FltObject [in]

An opaque pointer for the volume or instance. Be aware that the associated volume must be a local file system volume. 


### -param IsWritable [out]

A pointer to a caller-allocated Boolean variable that receives <b>TRUE</b> if the volume is writable; <b>FALSE</b> otherwise. 


## -returns



<b>FltIsVolumeWritable</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltIsVolumeWritable</b> encountered a memory allocation failure. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The disk device does not support IOCTL_DISK_IS_WRITABLE requests. This is an error code.

</td>
</tr>
</table>
 




## -remarks



<b>FltIsVolumeWritable</b> sends an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_is_writable">IOCTL_DISK_IS_WRITABLE</a> request to the underlying storage device that is associated with the given volume or instance. 

In versions of Windows prior to Windows Vista, the <b>FltIsVolumeWritable</b> routine accepted only volumes, not instances. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_is_writable">IOCTL_DISK_IS_WRITABLE</a>
 

 

