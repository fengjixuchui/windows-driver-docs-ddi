---
UID: NI:ntddcdrm.IOCTL_CDROM_READ_TOC
title: IOCTL_CDROM_READ_TOC (ntddcdrm.h)
description: Returns the table of contents of the media. Obsolete, beginning with Windows Vista.
old-location: storage\ioctl_cdrom_read_toc.htm
tech.root: storage
ms.assetid: 4820dca5-7bbe-425d-9063-54450146f273
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_READ_TOC, IOCTL_CDROM_READ_TOC control, IOCTL_CDROM_READ_TOC control code [Storage Devices], k307_8e0f2b70-edd0-424e-abb4-a81ea9f382fe.xml, ntddcdrm/IOCTL_CDROM_READ_TOC, storage.ioctl_cdrom_read_toc
ms.topic: ioctl
f1_keywords:
 - "ntddcdrm/IOCTL_CDROM_READ_TOC"
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
- IOCTL_CDROM_READ_TOC
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_READ_TOC IOCTL


## -description



Returns the table of contents of the media.  Obsolete, beginning with Windows Vista.




## -ioctlparameters




### -input-buffer

Input buffer.


### -input-buffer-length

<i>
       Parameters.DeviceIoControl.OutputBufferLength</i> in the I/O stack location indicates the size, in bytes, of the buffer, which must be greater than or equal to  <b>sizeof</b>(CDROM_TOC).


### -output-buffer

The driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc">CDROM_TOC</a> data in the buffer at <i>Irp->AssociatedIrp.SystemBuffer</i>.


### -output-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc">CDROM_TOC</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_NO_MEDIA_IN_DEVICE, STATUS_DEVICE_NOT_READY, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_BUSY, or STATUS_VERIFY_REQUIRED.


## -remarks



Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc">CDROM_TOC</a>
 

 

