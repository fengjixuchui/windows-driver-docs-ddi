---
UID: NS:usbioctl._USB_NODE_CONNECTION_INFORMATION
title: _USB_NODE_CONNECTION_INFORMATION (usbioctl.h)
description: The USB_NODE_CONNECTION_INFORMATION structure is used with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION request to retrieve information about a USB port and connected device.
old-location: buses\usb_node_connection_information.htm
tech.root: usbref
ms.assetid: 1ed92343-c830-4e5e-a2f8-30b20057b1f0
ms.date: 05/07/2018
keywords: ["USB_NODE_CONNECTION_INFORMATION structure"]
ms.keywords: "*PUSB_NODE_CONNECTION_INFORMATION, PUSB_NODE_CONNECTION_INFORMATION, PUSB_NODE_CONNECTION_INFORMATION structure pointer [Buses], USB_NODE_CONNECTION_INFORMATION, USB_NODE_CONNECTION_INFORMATION structure [Buses], _USB_NODE_CONNECTION_INFORMATION, buses.usb_node_connection_information, usbioctl/PUSB_NODE_CONNECTION_INFORMATION, usbioctl/USB_NODE_CONNECTION_INFORMATION, usbstrct_3c58e495-9552-4e38-81ac-45c23d964825.xml"
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
req.typenames: USB_NODE_CONNECTION_INFORMATION, *PUSB_NODE_CONNECTION_INFORMATION
f1_keywords:
 - _USB_NODE_CONNECTION_INFORMATION
 - usbioctl/_USB_NODE_CONNECTION_INFORMATION
 - PUSB_NODE_CONNECTION_INFORMATION
 - usbioctl/PUSB_NODE_CONNECTION_INFORMATION
 - USB_NODE_CONNECTION_INFORMATION
 - usbioctl/USB_NODE_CONNECTION_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - USB_NODE_CONNECTION_INFORMATION
---

# _USB_NODE_CONNECTION_INFORMATION structure


## -description

The <b>USB_NODE_CONNECTION_INFORMATION</b> structure is used with the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</a>  request to retrieve information about a USB port and connected device.

## -struct-fields

### -field ConnectionIndex

A value that is greater than or equal to 1 that specifies the number of the port.

### -field DeviceDescriptor

A <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a> structure that reports the USB device descriptor that is returned by the attached device during enumeration.

### -field CurrentConfigurationValue

Contains the ID used with the SetConfiguration request to specify that current configuration of the device connected to the indicated port. For an explanation of this value, see section 9.4.7 in the Universal Serial Bus 3.1 Specification available at [USB Document Library](https://www.usb.org/documents).

### -field LowSpeed

A Boolean value that indicates whether the port and its connected device are operating at low speed. <b>TRUE</b> indicates that the port and its connected device are currently operating at a low speed. <b>FALSE</b> indicates otherwise.

### -field DeviceIsHub

A Boolean value that indicates if the device that is attached to the port is a hub. If <b>TRUE</b>, the device that is attached to the port is a hub. If <b>FALSE</b>, the device is not a hub.

### -field DeviceAddress

The USB-assigned, bus-relative address of the device that is attached to the port.

### -field NumberOfOpenPipes

The number of open USB pipes that are associated with the port.

### -field ConnectionStatus

A <a href="/windows-hardware/drivers/ddi/usbioctl/ne-usbioctl-_usb_connection_status">USB_CONNECTION_STATUS</a>-typed enumerator that indicates the connection status.

### -field PipeList

An array of <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_pipe_info">USB_PIPE_INFO</a> structures  that describes the open pipes that are associated with the port. Pipe descriptions include the schedule offset of the pipe and the associated endpoint descriptor. This information can be used to calculate bandwidth usage.

## -remarks

If there is no device connected to the USB port, <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</a> returns only information about the port. If a device is connected to the port, <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</b> returns information about both the port and the connected device.

The <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_information_ex">USB_NODE_CONNECTION_INFORMATION_EX</a> structure is an extended version of <b>USB_NODE_CONNECTION_INFORMATION</b>. The two structures are identical, except for one member. In <b>USB_NODE_CONNECTION_INFORMATION_EX</b>, the <b>LowSpeed</b> member is replaced by the <b>Speed</b> member. <b>LowSpeed</b> is a Boolean value, so when it is <b>TRUE</b>, the device is low speed. When it is <b>FALSE</b>, the device is high speed or full speed. Thus the <b>USB_NODE_CONNECTION_INFORMATION</b> structure cannot differentiate between high and full speeds. 

The <b>Speed</b> member of the <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_information_ex">USB_NODE_CONNECTION_INFORMATION_EX</a> structure is a UCHAR and it can specify any of the values of the <a href="/windows-hardware/drivers/ddi/usbspec/ne-usbspec-_usb_device_speed">USB_DEVICE_SPEED</a> enumerator.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information_ex">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a>



<a href="/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ne-usbioctl-_usb_connection_status">USB_CONNECTION_STATUS</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ne-usbspec-_usb_device_speed">USB_DEVICE_SPEED</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_information_ex">USB_NODE_CONNECTION_INFORMATION_EX</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_pipe_info">USB_PIPE_INFO</a>