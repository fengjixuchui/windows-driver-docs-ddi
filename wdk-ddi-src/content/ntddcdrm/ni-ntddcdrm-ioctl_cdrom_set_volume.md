---
UID: NI:ntddcdrm.IOCTL_CDROM_SET_VOLUME
title: IOCTL_CDROM_SET_VOLUME (ntddcdrm.h)
description: Resets the volume for its device's audio ports. Obsolete, beginning with Windows Vista.
old-location: storage\ioctl_cdrom_set_volume.htm
tech.root: storage
ms.assetid: 9331ad0b-42e0-4f20-9410-fb135f4791b0
ms.date: 03/29/2018
keywords: ["IOCTL_CDROM_SET_VOLUME IOCTL"]
ms.keywords: IOCTL_CDROM_SET_VOLUME, IOCTL_CDROM_SET_VOLUME control, IOCTL_CDROM_SET_VOLUME control code [Storage Devices], k307_d31efcd3-1072-49db-82d0-6ecce05a8964.xml, ntddcdrm/IOCTL_CDROM_SET_VOLUME, storage.ioctl_cdrom_set_volume
f1_keywords:
 - "ntddcdrm/IOCTL_CDROM_SET_VOLUME"
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: Obsolete, beginning with Windows Vista.
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
- ntddcdrm.h
api_name:
- IOCTL_CDROM_SET_VOLUME
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_SET_VOLUME IOCTL


## -description



Resets the volume for its device's audio ports.  Obsolete, beginning with Windows Vista.




## -ioctlparameters




### -input-buffer

The buffer at <i>Irp->AssociatedIrp.SystemBuffer</i> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_volume_control">VOLUME_CONTROL</a> value or values to be set. 


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> in the I/O stack location indicates the size, in bytes, of the buffer, which must be greater than or equal to  <b>sizeof</b>(VOLUME_CONTROL).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_DEVICE_NOT_READY, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR, STATUS_VERIFY_REQUIRED, or STATUS_INVALID_DEVICE_REQUEST.


## -remarks



Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_volume_control">VOLUME_CONTROL</a>
 

 

