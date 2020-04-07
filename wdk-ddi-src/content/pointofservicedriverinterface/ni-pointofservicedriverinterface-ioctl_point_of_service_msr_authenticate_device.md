---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE
title: IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE (pointofservicedriverinterface.h)
description: This IO control function authenticates the magnetic stripe reader (MSR).
old-location: pos\ioctl_point_of_service_msr_authenticate_device.htm
tech.root: pos
ms.assetid: fc6b719d-3e05-4ff5-9d81-1e9326ff4ad4
ms.date: 02/23/2018
keywords: ["IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE, IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE control, IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE, pos.ioctl_point_of_service_msr_authenticate_device
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE"
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
- IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE IOCTL


## -description


This IO control function authenticates the magnetic stripe reader (MSR).


## -ioctlparameters




### -input-buffer

Pointer to the input buffer, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_msr_authenticate_device">MSR_AUTHENTICATE_DEVICE</a> variable.


### -input-buffer-length

Size of the input buffer, in bytes. Set to sizeof(<b>MSR_AUTHENTICATE_DEVICE</b>).


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

## -remarks

To get extended error information, call <a href="https://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following are common error values:

- STATUS_ACCESS_DENIED: The device is currently claimed by another client.

- STATUS_NOT_SUPPORTED: The device does not support authentication.
