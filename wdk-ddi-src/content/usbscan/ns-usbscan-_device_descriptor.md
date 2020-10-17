---
UID: NS:usbscan._DEVICE_DESCRIPTOR
title: _DEVICE_DESCRIPTOR (usbscan.h)
description: The DEVICE_DESCRIPTOR structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_DEVICE_DESCRIPTOR.
old-location: image\device_descriptor.htm
tech.root: image
ms.assetid: 15ad337a-0b33-48ba-98cf-6aff2698e2ba
ms.date: 05/03/2018
keywords: ["DEVICE_DESCRIPTOR structure"]
ms.keywords: "*PDEVICE_DESCRIPTOR, DEVICE_DESCRIPTOR, DEVICE_DESCRIPTOR structure [Imaging Devices], PDEVICE_DESCRIPTOR, PDEVICE_DESCRIPTOR structure pointer [Imaging Devices], _DEVICE_DESCRIPTOR, image.device_descriptor, stifnc_1b07d50b-5530-47d4-a212-54305a0fef7a.xml, usbscan/DEVICE_DESCRIPTOR, usbscan/PDEVICE_DESCRIPTOR"
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
targetos: Windows
req.typenames: DEVICE_DESCRIPTOR, *PDEVICE_DESCRIPTOR
f1_keywords:
 - _DEVICE_DESCRIPTOR
 - usbscan/_DEVICE_DESCRIPTOR
 - PDEVICE_DESCRIPTOR
 - usbscan/PDEVICE_DESCRIPTOR
 - DEVICE_DESCRIPTOR
 - usbscan/DEVICE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbscan.h
api_name:
 - DEVICE_DESCRIPTOR
---

# _DEVICE_DESCRIPTOR structure


## -description

The DEVICE_DESCRIPTOR structure is used as a parameter to <a href="/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="/windows-hardware/drivers/ddi/usbscan/ni-usbscan-ioctl_get_device_descriptor">IOCTL_GET_DEVICE_DESCRIPTOR</a>.

## -struct-fields

### -field usVendorId

Vendor identifier.

### -field usProductId

Device product identifier.

### -field usBcdDevice

BCD-encoded device version number.

### -field usLanguageId

<i>Not used</i>.