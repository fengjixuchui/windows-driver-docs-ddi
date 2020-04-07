---
UID: NE:udecxusbdevice._UDECX_ENDPOINT_TYPE
title: _UDECX_ENDPOINT_TYPE (udecxusbdevice.h)
description: Defines values for endpoint types supported by a virtual USB device.
old-location: buses\udecx_endpoint_type.htm
tech.root: usbref
ms.assetid: EFA5DDC0-9E6B-450E-B191-1DA9FBAC269C
ms.date: 05/07/2018
keywords: ["_UDECX_ENDPOINT_TYPE enumeration"]
ms.keywords: "*PUDECX_ENDPOINT_TYPE, UDECX_ENDPOINT_TYPE, UDECX_ENDPOINT_TYPE enumeration [Buses], UdecxEndpointTypeDynamic, UdecxEndpointTypeInvalid, UdecxEndpointTypeSimple, _UDECX_ENDPOINT_TYPE, buses.udecx_endpoint_type, udecxusbdevice/UDECX_ENDPOINT_TYPE, udecxusbdevice/UdecxEndpointTypeDynamic, udecxusbdevice/UdecxEndpointTypeInvalid, udecxusbdevice/UdecxEndpointTypeSimple"
f1_keywords:
 - "udecxusbdevice/UDECX_ENDPOINT_TYPE"
req.header: udecxusbdevice.h
req.include-header: Udecx.h
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
- UdecxUsbDevice.h
api_name:
- UDECX_ENDPOINT_TYPE
product:
- Windows
targetos: Windows
req.typenames: UDECX_ENDPOINT_TYPE, *PUDECX_ENDPOINT_TYPE
---

# _UDECX_ENDPOINT_TYPE enumeration


## -description


Defines values for endpoint types supported by a virtual USB device.


## -enum-fields




### -field UdecxEndpointTypeInvalid

The endpoint is not of a valid type.


### -field UdecxEndpointTypeSimple

The endpoint is defined in the first (and only) interface setting of the interface. That device has only one configuration. The client driver creates all endpoints before the device is detected. 


### -field UdecxEndpointTypeDynamic

The endpoint is dynamically created in the client driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a> callback.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">USB endpoints</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitsetendpointstype">UdecxUsbDeviceInitSetEndpointsType</a>
 

 

