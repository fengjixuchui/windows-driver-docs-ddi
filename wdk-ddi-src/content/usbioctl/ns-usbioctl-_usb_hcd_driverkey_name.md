---
UID: NS:usbioctl._USB_HCD_DRIVERKEY_NAME
title: _USB_HCD_DRIVERKEY_NAME (usbioctl.h)
description: The USB_HCD_DRIVERKEY_NAME structure is used with the IOCTL_GET_HCD_DRIVERKEY_NAME I/O control request to retrieve the driver key in the registry for the USB host controller driver.
old-location: buses\usb_hcd_driverkey_name.htm
tech.root: usbref
ms.assetid: 01161a61-c52a-4a0e-b680-a8c3a224c2e5
ms.date: 05/07/2018
keywords: ["USB_HCD_DRIVERKEY_NAME structure"]
ms.keywords: "*PUSB_HCD_DRIVERKEY_NAME, PUSB_HCD_DRIVERKEY_NAME, PUSB_HCD_DRIVERKEY_NAME structure pointer [Buses], USB_HCD_DRIVERKEY_NAME, USB_HCD_DRIVERKEY_NAME structure [Buses], _USB_HCD_DRIVERKEY_NAME, buses.usb_hcd_driverkey_name, usbioctl/PUSB_HCD_DRIVERKEY_NAME, usbioctl/USB_HCD_DRIVERKEY_NAME, usbstrct_f8c10863-dd1e-4771-b243-319a24f69f2a.xml"
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
req.typenames: USB_HCD_DRIVERKEY_NAME, *PUSB_HCD_DRIVERKEY_NAME
f1_keywords:
 - _USB_HCD_DRIVERKEY_NAME
 - usbioctl/_USB_HCD_DRIVERKEY_NAME
 - PUSB_HCD_DRIVERKEY_NAME
 - usbioctl/PUSB_HCD_DRIVERKEY_NAME
 - USB_HCD_DRIVERKEY_NAME
 - usbioctl/USB_HCD_DRIVERKEY_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - USB_HCD_DRIVERKEY_NAME
---

# _USB_HCD_DRIVERKEY_NAME structure


## -description

The <b>USB_HCD_DRIVERKEY_NAME</b> structure is used with the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_get_hcd_driverkey_name">IOCTL_GET_HCD_DRIVERKEY_NAME</a> I/O control request to retrieve the driver key in the registry for the USB host controller driver.

## -struct-fields

### -field ActualLength

The length, in bytes, of the string in the <b>DriverKeyName</b> member.

### -field DriverKeyName

A NULL-terminated Unicode driver key name for the USB host controller.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_get_hcd_driverkey_name">IOCTL_GET_HCD_DRIVERKEY_NAME</a>



<a href="/windows-hardware/drivers/ddi/index">USB Structures</a>