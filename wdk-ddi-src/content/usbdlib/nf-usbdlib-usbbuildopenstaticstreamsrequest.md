---
UID: NF:usbdlib.UsbBuildOpenStaticStreamsRequest
title: UsbBuildOpenStaticStreamsRequest function (usbdlib.h)
description: The UsbBuildOpenStaticStreamsRequest inline function formats an URB structure for an open-streams request. The request opens streams associated with the specified bulk endpoint.
old-location: buses\usbbuildopenbasicstreamsrequest.htm
tech.root: usbref
ms.assetid: B514B88E-2D1F-43F1-BF70-BC49294CFE93
ms.date: 05/07/2018
ms.keywords: UsbBuildOpenStaticStreamsRequest, UsbBuildOpenStaticStreamsRequest function [Buses], buses.usbbuildopenbasicstreamsrequest, usbdlib/UsbBuildOpenStaticStreamsRequest
ms.topic: function
f1_keywords:
 - "usbdlib/UsbBuildOpenStaticStreamsRequest"
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
- Usbdlib.h
api_name:
- UsbBuildOpenStaticStreamsRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# UsbBuildOpenStaticStreamsRequest function


## -description


The <b>UsbBuildOpenStaticStreamsRequest</b> inline function formats an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> structure for an open-streams request. The request opens streams associated with the specified bulk endpoint.


## -parameters




### -param Urb [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> structure to be formatted for the open-stream request (URB_FUNCTION_OPEN_STATIC_STREAMS). The caller must allocate nonpaged pool for this <b>URB</b>.




### -param PipeHandle [in]

An opaque handle for the pipe associated with the endpoint that contains the streams to open.

The client driver obtains <b>PipeHandle</b> from a previous select-configuration request (URB_FUNCTION_SELECT_CONFIGURATION) or a select-interface request (URB_FUNCTION_SELECT_INTERFACE). 


### -param NumberOfStreams [in]

The number of streams to open. The <b>NumberOfStreams</b> value indicates the number of elements in the array pointed to by <b>Streams</b>. This value must be greater than zero and less than or equal to the maximum number of streams supported by the host controller hardware. To get the maximum number of supported streams, call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406230(v=vs.85)">USBD_QueryUsbCapability</a>. 

The number streams must also be less than or equal to the maximum number of streams supported by the USB device. To get that number, inspect the endpoint companion descriptor. 

In the <b>NumberOfStreams</b> value, specify lesser of two values supported by the host controller and the USB device.


### -param StreamInfoArray [in]

Pointer to a caller-allocated, initialized array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_usbd_stream_information">USBD_STREAM_INFORMATION</a> structures. The length of the array depends on the number of streams to open and must be the same as the <b>NumberOfStreams</b> value.


## -returns



This function does not return a value.




## -remarks



For a code example that shows the URB format required for an open-streams request, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">How to Open and Close Static Streams in a USB Bulk Endpoint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_open_static_streams">_URB_OPEN_STATIC_STREAMS</a>
 

 

