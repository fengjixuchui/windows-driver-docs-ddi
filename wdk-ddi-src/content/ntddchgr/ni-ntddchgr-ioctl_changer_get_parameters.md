---
UID: NI:ntddchgr.IOCTL_CHANGER_GET_PARAMETERS
title: IOCTL_CHANGER_GET_PARAMETERS (ntddchgr.h)
description: Returns the parameters of the device.
old-location: storage\ioctl_changer_get_parameters.htm
tech.root: storage
ms.assetid: c4a6faa4-f3ea-4504-8d3b-a34465c90273
ms.date: 03/29/2018
ms.keywords: IOCTL_CHANGER_GET_PARAMETERS, IOCTL_CHANGER_GET_PARAMETERS control, IOCTL_CHANGER_GET_PARAMETERS control code [Storage Devices], k307_e3288dd0-4585-40de-aa5a-499c596aa75b.xml, ntddchgr/IOCTL_CHANGER_GET_PARAMETERS, storage.ioctl_changer_get_parameters
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
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
- Ntddchgr.h
api_name:
- IOCTL_CHANGER_GET_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CHANGER_GET_PARAMETERS IOCTL


## -description



Returns the parameters of the device.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(GET_CHANGER_PARAMETERS).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH or STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>
 

 

