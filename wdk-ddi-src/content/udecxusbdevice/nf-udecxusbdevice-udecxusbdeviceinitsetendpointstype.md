---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitSetEndpointsType
title: UdecxUsbDeviceInitSetEndpointsType function (udecxusbdevice.h)
description: Indicates the type of endpoint (simple or dynamic) in the initialization parameters that the client driver uses to create the virtual USB device.
old-location: buses\udecxusbdeviceinitsetendpointstype.htm
tech.root: usbref
ms.assetid: 44760191-77DD-40A9-AA11-AE8AB55AB307
ms.date: 05/07/2018
keywords: ["UdecxUsbDeviceInitSetEndpointsType function"]
ms.keywords: UdecxUsbDeviceInitSetEndpointsType, UdecxUsbDeviceInitSetEndpointsType function [Buses], buses.udecxusbdeviceinitsetendpointstype, udecxusbdevice/UdecxUsbDeviceInitSetEndpointsType
f1_keywords:
 - "udecxusbdevice/UdecxUsbDeviceInitSetEndpointsType"
 - "UdecxUsbDeviceInitSetEndpointsType"
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxUsbDeviceInitSetEndpointsType
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceInitSetEndpointsType function


## -description


Indicates the type of endpoint (simple or dynamic) in the initialization parameters that the client driver uses to create the virtual USB device.


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>. 


### -param UdecxEndpointType [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/ne-udecxusbdevice-_udecx_endpoint_type">UDECX_ENDPOINT_TYPE</a>-type value that indicates the type of USB endpoint.


## -remarks



Before creating the virtual USB device, the client driver must indicate the type of endpoint it supports. It can support one of two types (defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/ne-udecxusbdevice-_udecx_endpoint_type">UDECX_ENDPOINT_TYPE</a>): 

<ul>
<li>Simple endpoint-The client driver creates all endpoint objects before plugging in the device. The device must have only one configuration and one interface setting per interface.
</li>
<li>Dynamic endpoint-The client creates endpoint objects in the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a> callback function.
The USB device emulation  class extension (UdeCx) invokes the driver's implementation when it gets a request to add or configure endpoints.</li>
</ul>
The <i>UdecxUsbDeviceInit</i> is an opaque structure that contains pointers to callback functions related to endpoints. If the client driver supports dynamic endpoints, then these callback functions must be implemented by the driver:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoint_add">EVT_UDECX_USB_DEVICE_ENDPOINT_ADD</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_default_endpoint_add">EVT_UDECX_USB_DEVICE_DEFAULT_ENDPOINT_ADD</a>
</li>
</ul>
Before calling this method, the client driver must have set those pointers by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks">UdecxUsbDeviceInitSetStateChangeCallbacks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">USB endpoints</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks">UdecxUsbDeviceInitSetStateChangeCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

