---
UID: NF:usbdlib.USBD_IsochUrbAllocate
title: USBD_IsochUrbAllocate function (usbdlib.h)
description: The USBD_IsochUrbAllocate routine allocates and formats a URB structure for an isochronous transfer request.
old-location: buses\usbd_isochurballocate.htm
tech.root: usbref
ms.assetid: 357FB967-C9D8-468C-AA14-4EF071D55D7B
ms.date: 06/24/2019
ms.keywords: USBD_IsochUrbAllocate, USBD_IsochUrbAllocate routine [Buses], buses.usbd_isochurballocate, usbdlib/USBD_IsochUrbAllocate
ms.topic: function
f1_keywords:
 - "usbdlib/USBD_IsochUrbAllocate"
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
req.lib: Usbdex.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbdex.lib
- Usbdex.dll
api_name:
- USBD_IsochUrbAllocate
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_IsochUrbAllocate function


## -description


The  <b>USBD_IsochUrbAllocate</b> routine allocates and formats a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> structure for an isochronous transfer request.



<b>Note for Windows Driver Framework (WDF) Drivers:  </b>If your client driver is a WDF-based driver, then you must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicecreateisochurb">WdfUsbTargetDeviceCreateIsochUrb</a> method instead of <b>USBD_IsochUrbAllocate</b> to allocate memory for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> structure.


## -parameters




### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_createhandle">USBD_CreateHandle</a> routine.


### -param NumberOfIsochPacket [in]

Specifies the maximum number of isochronous packets required to perform the transfer. The transfer buffer is described in a variable-length array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_usbd_iso_packet_descriptor">USBD_ISO_PACKET_DESCRIPTOR</a> structures that stores information about each packet, such as byte offset of the packet within the buffer. The array is specified in the <b>IsoPacket</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_isoch_transfer">_URB_ISOCH_TRANSFER</a> structure, which is used to define the format of an isochronous request URB.


### -param Urb [out]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> structure,  which receives the URB allocated by <b>USBD_IsochUrbAllocate</b>. All members of the URB structure are set to zero. The allocated URB is large enough to hold the  maximum number of isochronous packets indicated by <b>NumberOfIsochPacket</b>. 

The client driver must free the URB when the driver has finished using it by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_urbfree">USBD_UrbFree</a>.


## -returns



The <b>USBD_IsochUrbAllocate</b> routine returns STATUS_SUCCESS if the request is successful. Otherwise,  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_urballocate">USBD_UrbAllocate</a> sets <i>Urb</i> to NULL and returns an NT status failure code. 

Possible values include, but are not limited to, STATUS_INVALID_PARAMETER, which  indicates the caller passed in NULL to <i>USBDHandle</i> or <i>Urb</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/how-to-add-xrb-support-for-client-drivers">Allocating and Building URBs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">How to Transfer Data to USB Isochronous Endpoints</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_usbd_iso_packet_descriptor">USBD_ISO_PACKET_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_isoch_transfer">_URB_ISOCH_TRANSFER</a>
 

 

