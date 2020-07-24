---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE
title: IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE (pointofservicedriverinterface.h)
description: This I/O control function is called when a client is ready to relinquish its claim on a device.
old-location: pos\ioctl_point_of_service_release_device.htm
tech.root: pos
ms.assetid: 623feb2b-8c49-41e8-9de5-d5955843c6f7
ms.date: 02/23/2018
keywords: ["IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE, IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE control, IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE, pos.ioctl_point_of_service_release_device
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE"
 - "IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE"
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
- pointofservicedriverinterface.h
api_name:
- IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE IOCTL


## -description


This I/O control function is called when a client is ready to relinquish its claim on a device.


## -ioctlparameters




### -input-buffer

Not used with this operation; set to <b>NULL</b>.


### -input-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

## -remarks

To get extended error information, call <a href="https://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values:

- STATUS_ACCESS_DENIED: The device is currently claimed by another client.

- STATUS_DEVICE_NOT_READY: The POS library has not been successfully initialized.

The driver can handle this IOCTL by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/nf-poscx-poscxreleasedevice">PosCxReleaseDevice</a>.

To use this IOCTL, the client must have previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device">IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE</a>.
