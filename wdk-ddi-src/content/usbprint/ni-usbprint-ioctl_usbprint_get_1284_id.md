---
UID: NI:usbprint.IOCTL_USBPRINT_GET_1284_ID
title: IOCTL_USBPRINT_GET_1284_ID (usbprint.h)
description: The IOCTL_USBPRINT_GET_1284_ID control code allows upper-layer software (such as a language monitor), to request and obtain the printer's IEEE 1284 device ID string.
old-location: print\ioctl_usbprint_get_1284_id.htm
tech.root: print
ms.assetid: b5c5a0e4-0fd9-4950-ac38-4bf58a0af077
ms.date: 04/20/2018
ms.keywords: IOCTL_USBPRINT_GET_1284_ID, IOCTL_USBPRINT_GET_1284_ID control, IOCTL_USBPRINT_GET_1284_ID control code [Print Devices], print.ioctl_usbprint_get_1284_id, usbioctl_4b1e9092-6483-4603-b690-a5e655a73670.xml, usbprint/IOCTL_USBPRINT_GET_1284_ID
ms.topic: ioctl
req.header: usbprint.h
req.include-header: 
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
- usbprint.h
api_name:
- IOCTL_USBPRINT_GET_1284_ID
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USBPRINT_GET_1284_ID IOCTL


## -description


The <b>IOCTL_USBPRINT_GET_1284_ID</b> control code allows upper-layer software (such as a language monitor), to request and obtain the printer's IEEE 1284 device ID string.


## -ioctlparameters




### -input-buffer

Not used in this operation; set this parameter to <b>NULL</b>.


### -input-buffer-length

Not used in this operation; set this parameter to 0.


### -output-buffer

The output buffer will contain UCHAR data. On success this buffer can hold the following: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the device ID; and a null terminator. An IEEE 1284 device ID can be up to 64 KB in size. On failure, if <b>GetLastError</b>returns the error code <b>STATUS_BUFFER_TOO_SMALL</b>, the output buffer was not large enough to hold the data intended for it.


### -output-buffer-length

The output buffer must be large enough to contain a two-byte quantity holding the length of the device's IEEE 1284 device ID, the device ID (up to 64 KB in size), and a terminating null.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

