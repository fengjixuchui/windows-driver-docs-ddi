---
UID: NI:ntddcdrm.IOCTL_CDROM_READ_TOC_EX
title: IOCTL_CDROM_READ_TOC_EX (ntddcdrm.h)
description: Queries the target device for the table of contents (TOC), the program memory area (PMA), and the absolute time in pregroove (ATIP).
old-location: storage\ioctl_cdrom_read_toc_ex.htm
tech.root: storage
ms.assetid: 279df233-9164-4c80-b31f-1d4cdc1073fa
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_READ_TOC_EX, IOCTL_CDROM_READ_TOC_EX control, IOCTL_CDROM_READ_TOC_EX control code [Storage Devices], k307_5206dcdd-936b-4d6f-b51a-4407e54814ea.xml, ntddcdrm/IOCTL_CDROM_READ_TOC_EX, storage.ioctl_cdrom_read_toc_ex
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows XP and later operating systems.
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
- IOCTL_CDROM_READ_TOC_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_READ_TOC_EX IOCTL


## -description



Queries the target device for the table of contents (TOC), the program memory area (PMA), and the absolute time in pregroove (ATIP). If the media is not a CD-ROM and does not support a TOC, this IOCTL returns information similar to that of a CD-ROM TOC. This is required for compatibility with some legacy initiator environments. 




## -ioctlparameters




### -input-buffer

<b>Irp->AssociatedIrp.SystemBuffer</b> points to a buffer of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_read_toc_ex">CDROM_READ_TOC_EX</a> whose contents indicate what information should be retrieved from the target device. 

<b>Parameters.Read.Length</b> in the I/O stack location indicates the size, in bytes, of the information to be retrieved from the target device. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the input buffer, which must be >= <b>sizeof</b>(CDROM_READ_TOC_EX).


### -output-buffer

The driver returns the query data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the output buffer, which must be >= MINIMUM_CDROM_READ_TOC_EX_SIZE.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_read_toc_ex">CDROM_READ_TOC_EX</a>
 

 

