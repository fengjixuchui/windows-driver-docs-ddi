---
UID: NI:ntddpcm.IOCTL_SOCKET_INFORMATION
title: IOCTL_SOCKET_INFORMATION (ntddpcm.h)
description: This request retrieves socket information for the socket that is indicated by the caller.
old-location: pcmcia\ioctl_socket_information.htm
tech.root: PCMCIA
ms.assetid: 95563d68-e812-4c62-9668-8cb25b4735aa
ms.date: 02/15/2018
keywords: ["IOCTL_SOCKET_INFORMATION IOCTL"]
ms.keywords: IOCTL_SOCKET_INFORMATION, IOCTL_SOCKET_INFORMATION control, IOCTL_SOCKET_INFORMATION control code [Buses], PCMCIA.ioctl_socket_information, memcdref_8730c03b-fc86-4d43-8aa9-6d15abcfa2d0.xml, ntddpcm/IOCTL_SOCKET_INFORMATION
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
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
 - IOCTL_SOCKET_INFORMATION
 - ntddpcm/IOCTL_SOCKET_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddpcm.h
api_name:
 - IOCTL_SOCKET_INFORMATION
---

# IOCTL_SOCKET_INFORMATION IOCTL


## -description

This request retrieves socket information for the socket that is indicated by the caller.

## -ioctlparameters

### -input-buffer

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION).

The caller initializes the <b>Socket</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/ns-ntddpcm-_pcmcia_socket_information">PCMCIA_SOCKET_INFORMATION</a> structure at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION).

### -output-buffer

The PCMCIA bus driver stores the requested socket data in a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/ns-ntddpcm-_pcmcia_socket_information">PCMCIA_SOCKET_INFORMATION</a> at the beginning of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

The size of the requested socket data.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes read. 

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

If <b>InputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.

If <b>OutputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.

If the bus driver cannot identify a socket that is associated with the socket number indicated in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/ns-ntddpcm-_pcmcia_socket_information">PCMCIA_SOCKET_INFORMATION</a>, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If there is no card in the indicated socket, the <b>Status</b> field is set to STATUS_UNSUCCESSFUL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddpcm/ns-ntddpcm-_pcmcia_socket_information">PCMCIA_SOCKET_INFORMATION</a>

