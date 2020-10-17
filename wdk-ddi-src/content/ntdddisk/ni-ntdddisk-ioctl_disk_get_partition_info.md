---
UID: NI:ntdddisk.IOCTL_DISK_GET_PARTITION_INFO
title: IOCTL_DISK_GET_PARTITION_INFO (ntdddisk.h)
description: Returns information about the type, size, and nature of a disk partition. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_get_partition_info.htm
tech.root: storage
ms.assetid: 4ac10da1-955e-471d-9d99-64f48e3c96a7
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_GET_PARTITION_INFO IOCTL"]
ms.keywords: IOCTL_DISK_GET_PARTITION_INFO, IOCTL_DISK_GET_PARTITION_INFO control, IOCTL_DISK_GET_PARTITION_INFO control code [Storage Devices], k307_6643c9ae-b43e-44a9-b1ca-4963c170b9d1.xml, ntdddisk/IOCTL_DISK_GET_PARTITION_INFO, storage.ioctl_disk_get_partition_info
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_DISK_GET_PARTITION_INFO
 - ntdddisk/IOCTL_DISK_GET_PARTITION_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntdddisk.h
api_name:
 - IOCTL_DISK_GET_PARTITION_INFO
---

# IOCTL_DISK_GET_PARTITION_INFO IOCTL


## -description

Returns information about the type, size, and nature of a disk partition. (Floppy drivers need not handle this request.)

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The driver returns the <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information">PARTITION_INFORMATION</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(PARTITION_INFORMATION).

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information">PARTITION_INFORMATION</a>