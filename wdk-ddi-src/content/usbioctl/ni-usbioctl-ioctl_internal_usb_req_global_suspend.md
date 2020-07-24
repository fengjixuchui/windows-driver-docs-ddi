---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND
title: IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND (usbioctl.h)
description: The IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND IOCTL is used by the USB hub driver. Do not use.
old-location: buses\ioctl_internal_usb_req_global_suspend.htm
tech.root: usbref
ms.assetid: e724ae02-642d-464c-b1d2-e43a657b4e9c
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND IOCTL"]
ms.keywords: IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND, IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND control, IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND control code [Buses], buses.ioctl_internal_usb_req_global_suspend, usbioctl/IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND
f1_keywords:
 - "usbioctl/IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND"
 - "IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND"
req.header: usbioctl.h
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
- Usbioctl.h
api_name:
- IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND IOCTL


## -description


 The <b>IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND</b> IOCTL is used by the USB hub driver. Do not use.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).



