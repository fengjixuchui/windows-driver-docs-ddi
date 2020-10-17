---
UID: NI:usbioctl.IOCTL_USB_GET_NODE_CONNECTION_NAME
title: IOCTL_USB_GET_NODE_CONNECTION_NAME (usbioctl.h)
description: The IOCTL_USB_GET_NODE_CONNECTION_NAME I/O control request is used with the USB_NODE_CONNECTION_NAME structure to retrieve the symbolic link name of the hub that is attached to the downstream port.IOCTL_USB_GET_NODE_CONNECTION_NAME is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).
old-location: buses\ioctl_usb_get_node_connection_name.htm
tech.root: usbref
ms.assetid: c4374b79-5143-4a35-aa4f-07fee7ea4fd3
ms.date: 05/07/2018
keywords: ["IOCTL_USB_GET_NODE_CONNECTION_NAME IOCTL"]
ms.keywords: IOCTL_USB_GET_NODE_CONNECTION_NAME, IOCTL_USB_GET_NODE_CONNECTION_NAME control, IOCTL_USB_GET_NODE_CONNECTION_NAME control code [Buses], buses.ioctl_usb_get_node_connection_name, usbioctl/IOCTL_USB_GET_NODE_CONNECTION_NAME, usbirp_d571c9e6-0caf-4746-bd69-b55fa6a3a407.xml
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
req.typenames: 
f1_keywords:
 - IOCTL_USB_GET_NODE_CONNECTION_NAME
 - usbioctl/IOCTL_USB_GET_NODE_CONNECTION_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - IOCTL_USB_GET_NODE_CONNECTION_NAME
---

# IOCTL_USB_GET_NODE_CONNECTION_NAME IOCTL


## -description

The <b>IOCTL_USB_GET_NODE_CONNECTION_NAME</b> I/O control request is used with the <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_name">USB_NODE_CONNECTION_NAME</a> structure to retrieve the symbolic link name of the hub that is attached to the downstream port.

<b>IOCTL_USB_GET_NODE_CONNECTION_NAME</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).

## -ioctlparameters

### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_name">USB_NODE_CONNECTION_NAME</a> structure. On input, the <b>ConnectionIndex</b> member of this structure must indicate the number of the port to check for an attached hub.

### -input-buffer-length

The size of a <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_name">USB_NODE_CONNECTION_NAME</a> structure.

### -output-buffer

<b>AssociatedIrp.SystemBuffer</b> points to a <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_name">USB_NODE_CONNECTION_NAME</a> structure. On output, this structure contains the symbolic name of the attached hub in the <b>HubName</b> member. If no hub is attached, the hub does not have a symbolic link, or the attached device is not a hub, <b>HubName</b>[0] will contain a value of UNICODE_NULL.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member contains the size, in bytes, of the entire <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_name">USB_NODE_CONNECTION_NAME</a> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The USB stack sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. The request reports success, even if no hub is attached, the attached hub has no symbolic link, or the attached device is not a hub.

Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_name">USB_NODE_CONNECTION_NAME</a>