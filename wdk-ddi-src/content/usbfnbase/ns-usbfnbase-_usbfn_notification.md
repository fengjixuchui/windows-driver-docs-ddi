---
UID: NS:usbfnbase._USBFN_NOTIFICATION
title: _USBFN_NOTIFICATION (usbfnbase.h)
description: Describes information about a Universal Serial Bus (USB) event notification that was received by using IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION.
old-location: buses\usbfn_notification.htm
tech.root: usbref
ms.assetid: 84B66823-F357-44DD-A401-79E27FA6B324
ms.date: 05/07/2018
keywords: ["USBFN_NOTIFICATION structure"]
ms.keywords: "*PUSBFN_NOTIFICATION, PUSBFN_NOTIFICATION, PUSBFN_NOTIFICATION structure pointer [Buses], USBFN_NOTIFICATION, USBFN_NOTIFICATION structure [Buses], _USBFN_NOTIFICATION, buses.usbfn_notification, usbfnbase/PUSBFN_NOTIFICATION, usbfnbase/USBFN_NOTIFICATION"
req.header: usbfnbase.h
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
targetos: Windows
req.typenames: USBFN_NOTIFICATION, *PUSBFN_NOTIFICATION
f1_keywords:
 - _USBFN_NOTIFICATION
 - usbfnbase/_USBFN_NOTIFICATION
 - PUSBFN_NOTIFICATION
 - usbfnbase/PUSBFN_NOTIFICATION
 - USBFN_NOTIFICATION
 - usbfnbase/USBFN_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnbase.h
api_name:
 - USBFN_NOTIFICATION
---

# _USBFN_NOTIFICATION structure


## -description

Describes information about a Universal Serial Bus (USB)  event notification that was 
		received by using <a href="/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_bus_event_notification">IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION</a>.

## -struct-fields

### -field Event

Bus notification indicated by a <a href="/windows-hardware/drivers/ddi/usbfnbase/ne-usbfnbase-_usbfn_event">USBFN_EVENT</a>-typed flag.

### -field u

### -field u.BusSpeed

The operating bus speed indicated by <a href="/windows-hardware/drivers/ddi/usbfnbase/ne-usbfnbase-_usbfn_bus_speed">USBFN_BUS_SPEED</a>-typed flags.

### -field u.SetupPacket

Describes a setup packet in a  <b>USB_DEFAULT_PIPE_SETUP_PACKET</b> structure for a control transfer to or from the default endpoint as indicated by a <b>USB_DEFAULT_PIPE_SETUP_PACKET</b>-typed flag.

### -field u.ConfigurationValue

The <b>bConfigurationValue</b> field of a USB configuration descriptor.

### -field u.PortType

Possible port types supported by a function controller indicated by a <a href="/windows-hardware/drivers/ddi/usbfnbase/ne-usbfnbase-_usbfn_port_type">USBFN_PORT_TYPE</a>-typed flag.

### -field u.AlternateInterface

Alternate setting of the interface indicated by <a href="/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_alternate_interface">ALTERNATE_INTERFACE</a>.