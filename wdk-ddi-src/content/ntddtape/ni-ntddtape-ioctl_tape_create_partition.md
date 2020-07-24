---
UID: NI:ntddtape.IOCTL_TAPE_CREATE_PARTITION
title: IOCTL_TAPE_CREATE_PARTITION (ntddtape.h)
description: Creates the specified number of fixed, select, or initiator partition(s) of the given size on the media.
old-location: storage\ioctl_tape_create_partition.htm
tech.root: storage
ms.assetid: da220281-a08d-4aeb-abb4-471aacb2461a
ms.date: 03/29/2018
keywords: ["IOCTL_TAPE_CREATE_PARTITION IOCTL"]
ms.keywords: IOCTL_TAPE_CREATE_PARTITION, IOCTL_TAPE_CREATE_PARTITION control, IOCTL_TAPE_CREATE_PARTITION control code [Storage Devices], k307_d1911c51-33f1-4c45-bbf0-ace7714fa53f.xml, ntddtape/IOCTL_TAPE_CREATE_PARTITION, storage.ioctl_tape_create_partition
f1_keywords:
 - "ntddtape/IOCTL_TAPE_CREATE_PARTITION"
 - "IOCTL_TAPE_CREATE_PARTITION"
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddtape.h
api_name:
- IOCTL_TAPE_CREATE_PARTITION
targetos: Windows
req.typenames: 
---

# IOCTL_TAPE_CREATE_PARTITION IOCTL


## -description



Creates the specified number of fixed, select, or initiator partition(s) of the given size on the media.




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_create_partition">TAPE_CREATE_PARTITION</a> that specifies the partition(s) to be created. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(TAPE_CREATE_PARTITION). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_MEDIA_WRITE_PROTECTED, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_INFO_LENGTH_MISMATCH, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ns-ntddtape-_tape_create_partition">TAPE_CREATE_PARTITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>
 

 

