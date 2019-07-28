---
UID: NI:hidclass.IOCTL_HID_ENABLE_WAKE_ON_SX
title: IOCTL_HID_ENABLE_WAKE_ON_SX (hidclass.h)
description: The IOCTL_HID_ENABLE_WAKE_ON_SX request is used to indicate the requirement for a device to be able to wake from system sleep.
old-location: hid\ioctl_hid_enable_wake_on_sx.htm
tech.root: hid
ms.assetid: E06B1444-F270-48A0-A096-E0289DD4DBBA
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_ENABLE_WAKE_ON_SX, IOCTL_HID_ENABLE_WAKE_ON_SX control, IOCTL_HID_ENABLE_WAKE_ON_SX control code [Human Input Devices], hid.ioctl_hid_enable_wake_on_sx, hidclass/IOCTL_HID_ENABLE_WAKE_ON_SX
ms.topic: ioctl
f1_keywords:
 - "hidclass/IOCTL_HID_ENABLE_WAKE_ON_SX"
req.header: hidclass.h
req.include-header: Hidclass.h
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
- hidclass.h
api_name:
- IOCTL_HID_ENABLE_WAKE_ON_SX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_ENABLE_WAKE_ON_SX IOCTL


## -description


The <b>IOCTL_HID_ENABLE_WAKE_ON_SX</b> 
   request is  used to indicate the  requirement for a device to be able to wake from system sleep.

User mode clients, including user mode driver framework (UMDF) drivers, use this IOCTL to let a device know about the "<i>wake from sleep</i>" requirement. The user mode clients use this IOCTL because they are not able to send an I/O request packet (IRP) to a device.


## -ioctlparameters




### -input-buffer

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member specifies the size, in bytes, of a requester-allocated output buffer. 


### -input-buffer-length

This is a buffer of size Boolean.


### -output-buffer

The <b>Irp->AssociatedIrp.SystemBuffer</b> member is a pointer to the requestor-allocated buffer that the HID class driver uses to return the Boolean value.  This Boolean value indicates whether or not the device is configured and ready to wake from system sleep. The pointer is cast as a pointer to Boolean: (PBOOLEAN)(Irp->AssociatedIrp.SystemBuffer).


### -output-buffer-length

This is a buffer of size Boolean.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

