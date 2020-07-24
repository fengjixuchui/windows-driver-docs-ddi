---
UID: NS:usbioctl._HUB_DEVICE_CONFIG_INFO_V1
title: _HUB_DEVICE_CONFIG_INFO_V1 (usbioctl.h)
description: The HUB_DEVICE_CONFIG_INFO structure is used in conjunction with the kernel-mode IOCTL, IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO to request to report information about a USB device and the hub to which the device is attached.
old-location: buses\hub_device_config_info.htm
tech.root: usbref
ms.assetid: 2e94cf01-6edf-40ca-b25e-ce7c125e4686
ms.date: 05/07/2018
keywords: ["_HUB_DEVICE_CONFIG_INFO_V1 structure"]
ms.keywords: "*PHUB_DEVICE_CONFIG_INFO, HUB_DEVICE_CONFIG_INFO, HUB_DEVICE_CONFIG_INFO structure [Buses], PHUB_DEVICE_CONFIG_INFO, PHUB_DEVICE_CONFIG_INFO structure pointer [Buses], _HUB_DEVICE_CONFIG_INFO_V1, buses.hub_device_config_info, usbioctl/HUB_DEVICE_CONFIG_INFO, usbioctl/PHUB_DEVICE_CONFIG_INFO"
f1_keywords:
 - "usbioctl/HUB_DEVICE_CONFIG_INFO"
 - "HUB_DEVICE_CONFIG_INFO"
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows XP and later operating systems.
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
- usbioctl.h
api_name:
- HUB_DEVICE_CONFIG_INFO
targetos: Windows
req.typenames: HUB_DEVICE_CONFIG_INFO, *PHUB_DEVICE_CONFIG_INFO
---

# _HUB_DEVICE_CONFIG_INFO_V1 structure


## -description


The <b>HUB_DEVICE_CONFIG_INFO</b> structure is used in conjunction with the kernel-mode IOCTL, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_get_device_config_info">IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO</a> to request to report information about a USB device and the hub to which the device is attached. 


## -struct-fields




### -field Version

Specifies the version number.  Must be set to 1. 


### -field Length

Specifies the size of the <b>HUB_DEVICE_CONFIG_INFO</b> structure. Must be set by the caller.


### -field HubFlags

Specifies the hub capabilities in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_cap_flags">USB_HUB_CAP_FLAGS</a> structure.  


### -field HardwareIds

The PnP hardware ID multi-string for the USB device in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_id_string">USB_ID_STRING</a> structure. 


### -field CompatibleIds

 PnP compatible ID multi-string for the USB device in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_id_string">USB_ID_STRING</a> structure. 


### -field DeviceDescription

Description of the device in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_id_string">USB_ID_STRING</a> structure. This may be set to <b>NULL</b>.


### -field Reserved
Reserved.
 


### -field UxdSettings





## -remarks




 The <b>Buffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_id_string">USB_ID_STRING</a> structure points to a string that contains <b>HardwareIds</b>, <b>CompatibleIds</b>, and <b>DeviceDescription</b> values.
The caller is responsible for releasing this string buffer, which is allocated by the hub driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_get_device_config_info">IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_cap_flags">USB_HUB_CAP_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_id_string">USB_ID_STRING</a>
 

 

