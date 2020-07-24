---
UID: NS:usbspec._USB_INTERFACE_DESCRIPTOR
title: _USB_INTERFACE_DESCRIPTOR (usbspec.h)
description: The USB_INTERFACE_DESCRIPTOR structure is used by USB client drivers to retrieve a USB-defined interface descriptor.
old-location: buses\usb_interface_descriptor.htm
tech.root: usbref
ms.assetid: 12378915-fa3d-4054-bb06-6eb8b292559c
ms.date: 05/07/2018
keywords: ["_USB_INTERFACE_DESCRIPTOR structure"]
ms.keywords: "*PUSB_INTERFACE_DESCRIPTOR, PUSB_INTERFACE_DESCRIPTOR, PUSB_INTERFACE_DESCRIPTOR structure pointer [Buses], USB_INTERFACE_DESCRIPTOR, USB_INTERFACE_DESCRIPTOR structure [Buses], _USB_INTERFACE_DESCRIPTOR, buses.usb_interface_descriptor, usbspec/PUSB_INTERFACE_DESCRIPTOR, usbspec/USB_INTERFACE_DESCRIPTOR, usbstrct_2b4503ac-895a-4e94-87b5-10f286ed0b90.xml"
f1_keywords:
 - "usbspec/USB_INTERFACE_DESCRIPTOR"
 - "USB_INTERFACE_DESCRIPTOR"
req.header: usbspec.h
req.include-header: Usb100.h
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
- usbspec.h
api_name:
- USB_INTERFACE_DESCRIPTOR
targetos: Windows
req.typenames: USB_INTERFACE_DESCRIPTOR, *PUSB_INTERFACE_DESCRIPTOR
---

# _USB_INTERFACE_DESCRIPTOR structure


## -description


The <b>USB_INTERFACE_DESCRIPTOR</b> structure is used by USB client drivers to retrieve a USB-defined interface descriptor.
The members of this structure are described in the Universal Serial Bus 3.1 Specification available at [USB Document Library](https://www.usb.org/documents). See section 9.6.5.

## -struct-fields




### -field bLength

The length, in bytes, of the descriptor.


### -field bDescriptorType

The descriptor type. <b>bDescriptor</b> must be set to USB_INTERFACE_DESCRIPTOR_TYPE.


### -field bInterfaceNumber

The index number of the interface.


### -field bAlternateSetting

The index number of the alternate setting of the interface.


### -field bNumEndpoints

The number of endpoints that are used by the interface, excluding the default status endpoint.


### -field bInterfaceClass

The class code of the device that the USB specification group assigned.


### -field bInterfaceSubClass

The subclass code of the device that the USB specification group assigned.


### -field bInterfaceProtocol

The protocol code of the device that the USB specification group assigned.


### -field iInterface

The index of a string descriptor that describes the interface. For information about this field, see section 9.6.5 in the "Universal Serial Bus Revision 2.0" specification  at <a href="https://www.usb.org/documents">USB Technology</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/previous-versions/ff538943(v=vs.85)">UsbBuildGetDescriptorRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_descriptor_request">_URB_CONTROL_DESCRIPTOR_REQUEST</a>
 

 

