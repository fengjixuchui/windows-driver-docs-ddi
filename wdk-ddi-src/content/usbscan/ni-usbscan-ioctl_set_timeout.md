---
UID: NI:usbscan.IOCTL_SET_TIMEOUT
title: IOCTL_SET_TIMEOUT (usbscan.h)
description: Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access.
old-location: image\ioctl_set_timeout.htm
tech.root: image
ms.assetid: 90403ef3-d86c-4e2b-842d-c121cce07a47
ms.date: 05/03/2018
ms.keywords: IOCTL_SET_TIMEOUT, IOCTL_SET_TIMEOUT control, IOCTL_SET_TIMEOUT control code [Imaging Devices], image.ioctl_set_timeout, stifnc_942a0b21-7e68-444d-8bf2-7f8388a8a8fc.xml, usbscan/IOCTL_SET_TIMEOUT
ms.topic: ioctl
req.header: usbscan.h
req.include-header: Usbscan.h
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
- Usbscan.h
api_name:
- IOCTL_SET_TIMEOUT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SET_TIMEOUT IOCTL


## -description


Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access.


## -ioctlparameters




### -input-buffer

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbscan/ns-usbscan-_usbscan_timeout">USBSCAN_TIMEOUT</a> structure.


### -input-buffer-length

Size of the input buffer.


### -output-buffer

<b>NULL</b>.


### -output-buffer-length

Zero.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



<h3><a id="ddk_ioctl_set_timeout_si"></a><a id="DDK_IOCTL_SET_TIMEOUT_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_SET_TIMEOUT I/O control code, the caller must specify the address of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbscan/ns-usbscan-_usbscan_timeout">USBSCAN_TIMEOUT</a> structure as the function's <i>lpInBuffer</i> parameter.

Using the USBSCAN_TIMEOUT structure's contents, the kernel-mode driver resets the time-out value for each type of operation: bulk IN read, bulk OUT write, or interrupt.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices">Accessing Kernel-Mode Drivers for Still Image Devices</a>.

<div class="alert"><b>Note</b>    The default time-out value is 120 seconds. The maximum time-out value is 214 seconds. Values greater than 214 seconds will cause transfer time-outs.</div>
<div> </div>
The IOCTL_SET_TIMEOUT I/O control code is available in Microsoft Windows Me, Windows XP and later operating systems versions.



